# Metryx Systems LLC — Static Site (Amplify + Route 53 Ready)

This repo contains your **mobile-optimized** static website and legal pages, ready for **AWS Amplify Hosting** with CI/CD and **Route 53** custom domain.

## Files
- `index.html` — main site (from your updated mobile-optimized HTML)
- `capability-statement.pdf` + `capability-statement.html`
- `privacy-policy.html`, `terms-of-service.html`
- `robots.txt`, `sitemap.xml`, `404.html`

## Deploy with GitHub → Amplify (auto-deploy on push)
1. Create a new GitHub repo (public or private).
2. Copy these files into the repo root and push:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Metryx static site"
   git branch -M main
   git remote add origin https://github.com/<YOUR-USERNAME>/metryxsystems-site.git
   git push -u origin main
   ```
3. AWS Console → **Amplify** → **Hosting** → **Connect app**.
4. Choose **GitHub**, authorize, select the repo and the `main` branch.
5. When asked about a framework, pick **No framework (static)** → **Save and deploy**.
6. Amplify builds and hosts your site. Future pushes to `main` auto-deploy.

## Add Custom Domain via Route 53 (HTTPS + www redirect)
1. In Amplify app → **Domain management** → **Add domain** → enter `metryxsystems.com`.
2. If your domain is in **Route 53**, Amplify will create A/AAAA **ALIAS** records automatically.
3. In the wizard, enable **redirect** from `www.metryxsystems.com` → `metryxsystems.com`.
4. **SSL** (HTTPS) is auto-provisioned via AWS Certificate Manager.
5. Verify: `https://metryxsystems.com` resolves and `https://www.metryxsystems.com` redirects to apex.

## Notes
- Button “Request Our Capability Statement” links to `capability-statement.pdf`.
- Update `sitemap.xml` if you publish under a non-apex path or different domain.
