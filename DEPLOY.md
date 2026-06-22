# Deploy Systems by Gee to GitHub + Netlify

Run these in a terminal, inside the `website` folder.
(`.gitignore` is already set up, so `node_modules`, `dist`, and the source photos are excluded.)

## 1. Remove the leftover broken git folder

PowerShell:
```powershell
Remove-Item -Recurse -Force .git
```
(or just delete the hidden `.git` folder in File Explorer)

## 2. Initialise and commit
```bash
git init -b main
git add .
git commit -m "Initial commit: Systems by Gee website"
```

## 3. Create the GitHub repo and push

If you have the GitHub CLI installed:
```bash
gh repo create systemsbygee-website --public --source=. --push
```

Or manually: create an empty repo at github.com (no README), then:
```bash
git remote add origin https://github.com/YOUR-USERNAME/systemsbygee-website.git
git push -u origin main
```

## 4. Deploy on Netlify (free)
1. Go to Netlify, "Add new site" then "Import an existing project".
2. Connect GitHub and pick the repo.
3. Netlify reads `netlify.toml` automatically: build command `npm run build`, publish directory `dist`. Just click Deploy.
4. Newsletter signups appear under Site settings then Forms (Netlify Forms, free).

## 5. Connect your domain
1. In Netlify, add your custom domain (systemsbygee.com).
2. In Cloudflare DNS, add the records Netlify gives you (or switch the domain to Netlify DNS).

## Run locally first (optional, to preview)
```bash
npm install
npm run dev
```
Then open the printed URL (usually http://localhost:4321).

---
After it is live, swap the placeholder Open Graph image if you want, and you can keep adding blog posts in `src/pages/blog/`.
