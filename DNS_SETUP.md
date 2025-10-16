# DNS Setup Guide for nuchegroup.com

## DNS Records to Add

Log in to your domain registrar (GoDaddy, Namecheap, Google Domains, etc.) and add the following DNS records:

### 1. A Records (for apex domain nuchegroup.com)

Add **FOUR** A records pointing to GitHub's IP addresses:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 3600 |
| A | @ | 185.199.109.153 | 3600 |
| A | @ | 185.199.110.153 | 3600 |
| A | @ | 185.199.111.153 | 3600 |

**Note:** `@` represents your root domain (nuchegroup.com)

### 2. CNAME Record (for www subdomain)

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | www | aantonuccio-ai.github.io | 3600 |

## Step-by-Step Instructions

### Step 1: Configure DNS Records
1. Log in to your domain registrar's control panel
2. Find the DNS management section (often called "DNS Settings", "DNS Management", or "Name Servers")
3. Add all FOUR A records listed above
4. Add the CNAME record for www
5. Save your changes

### Step 2: Configure GitHub Pages
1. Go to https://github.com/aantonuccio-ai/nuche_group
2. Click **Settings** → **Pages** (in left sidebar)
3. Under "Source", select:
   - Branch: **main**
   - Folder: **/ (root)**
4. Click **Save**
5. In the "Custom domain" field, enter: `nuchegroup.com`
6. Click **Save**
7. Wait a few minutes, then check the box "Enforce HTTPS"

### Step 3: Wait for DNS Propagation
- DNS changes can take 24-48 hours to fully propagate worldwide
- GitHub Pages will automatically provision a free SSL certificate
- You can check DNS propagation at: https://dnschecker.org

## Verification

After DNS propagates (usually 15-60 minutes), verify:

1. **Test apex domain**: https://nuchegroup.com
2. **Test www subdomain**: https://www.nuchegroup.com
3. **Check HTTPS**: Both should automatically redirect to HTTPS

## Troubleshooting

### DNS Not Propagating
- Clear your browser cache
- Try accessing from a different device/network
- Use https://dnschecker.org to check global propagation

### HTTPS Certificate Issues
- Wait 24 hours after DNS propagation
- Uncheck and recheck "Enforce HTTPS" in GitHub Pages settings
- Ensure CNAME file is in the repository root

### Domain Shows 404
- Verify CNAME file contains exactly: `nuchegroup.com`
- Check that GitHub Pages is enabled on the main branch
- Ensure all DNS records are correct

## Current Setup

- **GitHub Repository**: https://github.com/aantonuccio-ai/nuche_group
- **Custom Domain**: nuchegroup.com
- **HTTPS**: Automatically provided by GitHub Pages
- **CDN**: Automatically provided by GitHub Pages

## Support

If you need help:
- GitHub Pages Docs: https://docs.github.com/en/pages
- DNS Checker: https://dnschecker.org
- GitHub Support: https://support.github.com
