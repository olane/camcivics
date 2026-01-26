# The Cambridge Compass

A new static website for The Cambridge Compass.

## Getting Started

Open the `index.html` file in your web browser to view the page.

## Deployment

This website is intended to be hosted on GitHub Pages with a custom domain (cambridgecompass.org).

### GitHub Pages Setup

1. Push the code to your GitHub repository.
2. In the repository settings, go to the "Pages" section.
3. Select the `main` branch and the `/ (root)` folder as the source.
4. In the "Custom domain" field, enter `cambridgecompass.org` and click "Save".
5. GitHub will automatically create/update the `CNAME` file (which is already included in this repo).

### Cloudflare DNS Configuration

1. Log in to your Cloudflare dashboard.
2. Select the `cambridgecompass.org` domain.
3. Go to the DNS settings.
4. Add the following DNS records:
   - **Type**: `CNAME`
   - **Name**: `@` (or leave blank for root domain)
   - **Target**: `<your-username>.github.io` (replace with your actual GitHub username)
   - **Proxy status**: DNS only (gray cloud, not orange)
   
   OR if you want to use A records (more reliable):
   - **Type**: `A`
   - **Name**: `@`
   - **Target**: `185.199.108.153`
   - **Proxy status**: DNS only
   
   - **Type**: `A`
   - **Name**: `@`
   - **Target**: `185.199.109.153`
   - **Proxy status**: DNS only
   
   - **Type**: `A`
   - **Name**: `@`
   - **Target**: `185.199.110.153`
   - **Proxy status**: DNS only
   
   - **Type**: `A`
   - **Name**: `@`
   - **Target**: `185.199.111.153`
   - **Proxy status**: DNS only

5. Also add a CNAME for www subdomain (optional but recommended):
   - **Type**: `CNAME`
   - **Name**: `www`
   - **Target**: `<your-username>.github.io`
   - **Proxy status**: DNS only

### SSL/TLS Settings

1. In Cloudflare, go to SSL/TLS settings.
2. Set encryption mode to "Full" (not "Full (strict)" initially).
3. GitHub Pages will automatically provision an SSL certificate for your custom domain (this may take a few hours).

### Verification

After DNS propagation (usually 5-30 minutes), your site should be accessible at:
- `https://cambridgecompass.org`
- `https://www.cambridgecompass.org` (if you set up the www subdomain)

Note: It may take up to 24 hours for GitHub to fully provision the SSL certificate.
