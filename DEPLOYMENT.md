# 🚀 Deployment Guide - MÉTIS Works Landing Page

## Pre-Deployment Checklist

- [x] HTML validated
- [x] CSS optimized
- [x] Images exported from Figma
- [x] Responsive design tested
- [x] Meta tags added
- [x] Favicon configured
- [ ] Font licensing confirmed (Canela)
- [ ] Email link added
- [ ] Analytics tracking added
- [ ] Performance optimized

---

## 1. Netlify (Recommended - Easiest)

### Method A: Drag & Drop
1. Go to [netlify.com](https://www.netlify.com/)
2. Sign up or log in
3. Drag the entire `/Test` folder to the deploy zone
4. Done! Your site is live.

### Method B: Netlify CLI
```bash
# Install Netlify CLI
npm install -g netlify-cli

# Navigate to project
cd /Users/luisatrogu/Desktop/Test

# Deploy
netlify deploy --prod
```

**Custom Domain:**
- Go to Site Settings → Domain Management
- Add your custom domain
- Configure DNS records

**Continuous Deployment:**
- Connect to Git repository
- Auto-deploys on push to main branch

---

## 2. Vercel

### Deploy with Vercel CLI
```bash
# Install Vercel CLI
npm install -g vercel

# Navigate to project
cd /Users/luisatrogu/Desktop/Test

# Deploy
vercel --prod
```

### Deploy from Git
1. Push code to GitHub/GitLab/Bitbucket
2. Import project at [vercel.com](https://vercel.com/)
3. Configure and deploy

**Configuration:**
- Build Command: None (static site)
- Output Directory: `.` (root)
- Install Command: None

---

## 3. GitHub Pages

### Setup
```bash
# Initialize git (if not already)
cd /Users/luisatrogu/Desktop/Test
git init

# Create repository on GitHub first, then:
git add .
git commit -m "Initial commit: MÉTIS Works landing page"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/metis-works.git
git push -u origin main
```

### Enable GitHub Pages
1. Go to repository Settings
2. Navigate to Pages
3. Source: Deploy from main branch
4. Select root folder `/`
5. Save

**Your site will be at:**
`https://YOUR_USERNAME.github.io/metis-works/`

---

## 4. AWS S3 + CloudFront

### S3 Setup
```bash
# Install AWS CLI
# https://aws.amazon.com/cli/

# Configure
aws configure

# Create bucket
aws s3 mb s3://metis-works-landing

# Upload files
cd /Users/luisatrogu/Desktop/Test
aws s3 sync . s3://metis-works-landing --acl public-read

# Enable static website hosting
aws s3 website s3://metis-works-landing --index-document index.html
```

### CloudFront (CDN)
1. Go to CloudFront console
2. Create distribution
3. Origin: Your S3 bucket
4. Enable HTTPS
5. Add custom domain (optional)

**Benefits:**
- Global CDN
- HTTPS included
- Highly scalable
- Pay-as-you-go

---

## 5. Firebase Hosting

```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login
firebase login

# Initialize
cd /Users/luisatrogu/Desktop/Test
firebase init hosting

# Configure:
# - Public directory: .
# - Single-page app: No
# - Set up automatic builds: Optional

# Deploy
firebase deploy --only hosting
```

---

## Performance Optimization

### Before Deployment

#### 1. Minify CSS
```bash
# Using cssnano
npx cssnano styles.css styles.min.css
```

Then update HTML to reference `styles.min.css`

#### 2. Optimize SVGs
```bash
# Using SVGO
npx svgo assets/*.svg
```

#### 3. Add Cache Headers
Create `netlify.toml`:
```toml
[[headers]]
  for = "/*"
  [headers.values]
    Cache-Control = "public, max-age=31536000, immutable"

[[headers]]
  for = "/*.html"
  [headers.values]
    Cache-Control = "public, max-age=0, must-revalidate"
```

#### 4. Enable Compression
Most hosting platforms enable Gzip/Brotli automatically.

For S3, add metadata:
```bash
aws s3 cp . s3://metis-works-landing \
  --recursive \
  --content-encoding gzip \
  --exclude "*" \
  --include "*.css" \
  --include "*.html"
```

---

## Security Headers

### Add to hosting configuration:

**Netlify** (_headers file):
```
/*
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: geolocation=(), microphone=(), camera=()
```

**Vercel** (vercel.json):
```json
{
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        { "key": "X-Frame-Options", "value": "DENY" },
        { "key": "X-Content-Type-Options", "value": "nosniff" }
      ]
    }
  ]
}
```

---

## Custom Domain Setup

### DNS Configuration
Add these records to your domain registrar:

**For Netlify:**
```
A     @    75.2.60.5
CNAME www  your-site-name.netlify.app
```

**For Vercel:**
```
A     @    76.76.21.21
CNAME www  cname.vercel-dns.com
```

**For GitHub Pages:**
```
A     @    185.199.108.153
A     @    185.199.109.153
A     @    185.199.110.153
A     @    185.199.111.153
CNAME www  YOUR_USERNAME.github.io
```

### SSL/HTTPS
- **Netlify**: Automatic (Let's Encrypt)
- **Vercel**: Automatic
- **GitHub Pages**: Automatic
- **CloudFront**: Free AWS certificate
- **Firebase**: Automatic

---

## Analytics Integration

### Google Analytics
Add before `</head>`:
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Plausible (Privacy-friendly)
```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

---

## Monitoring

### Uptime Monitoring
- [UptimeRobot](https://uptimerobot.com/) - Free
- [Pingdom](https://www.pingdom.com/)
- [StatusCake](https://www.statuscake.com/)

### Performance Monitoring
- [Google PageSpeed Insights](https://pagespeed.web.dev/)
- [WebPageTest](https://www.webpagetest.org/)
- [GTmetrix](https://gtmetrix.com/)

---

## SEO Post-Deployment

1. **Submit to Search Engines:**
   - [Google Search Console](https://search.google.com/search-console)
   - [Bing Webmaster Tools](https://www.bing.com/webmasters)

2. **Create sitemap.xml:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://yourdomain.com/</loc>
    <lastmod>2025-11-07</lastmod>
    <priority>1.0</priority>
  </url>
</urlset>
```

3. **Create robots.txt:**
```
User-agent: *
Allow: /
Sitemap: https://yourdomain.com/sitemap.xml
```

---

## Troubleshooting

### Issue: Fonts not loading
**Solution:** Ensure Helvetica Neue is available or add web font fallback

### Issue: Images not showing after deployment
**Solution:** Check relative paths, ensure assets folder is uploaded

### Issue: Mobile layout broken
**Solution:** Verify viewport meta tag, test media queries

### Issue: Slow load time
**Solution:** Enable CDN, compress images, minify CSS

---

## Post-Deployment Checklist

- [ ] Site loads correctly
- [ ] All assets displaying
- [ ] Responsive design works
- [ ] SSL certificate active (HTTPS)
- [ ] Custom domain configured
- [ ] Analytics tracking
- [ ] Search engine submitted
- [ ] Performance score >90
- [ ] Mobile-friendly test passed
- [ ] Accessibility score >90

---

## Recommended Stack

**For Simple Landing Page:**
→ **Netlify** (free, easy, fast)

**For Scaling/Business:**
→ **Vercel** (edge functions, advanced features)

**For Enterprise:**
→ **AWS S3 + CloudFront** (full control, scalability)

**For Google Ecosystem:**
→ **Firebase Hosting** (integration with other Firebase services)

---

## Support & Resources

- [Web.dev - Performance](https://web.dev/performance/)
- [Can I Use](https://caniuse.com/) - Browser compatibility
- [Lighthouse](https://developers.google.com/web/tools/lighthouse) - Audit tool
- [W3C Validator](https://validator.w3.org/) - HTML validation

---

**Ready to deploy?** Choose your platform and follow the steps above.

**Questions?** Refer to platform-specific documentation or community forums.

