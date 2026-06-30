# Deployment Guide

## Quick Deploy Options

### Option 1: GitHub Pages (Recommended for Static Sites)

**Steps:**

1. **Create GitHub Repository**
   ```bash
   cd /Users/sharan.j/sharan-portfolio-resume
   git init
   git add .
   git commit -m "Initial commit: Animated SDET Portfolio"
   ```

2. **Push to GitHub**
   ```bash
   # Create repo on GitHub first, then:
   git remote add origin https://github.com/SharanAkash/portfolio.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to repository Settings
   - Navigate to Pages section
   - Select "main" branch
   - Click Save
   - Site will be live at: `https://sharanakash.github.io/portfolio/`

**Pros:**
- ✅ Free hosting
- ✅ Custom domain support
- ✅ HTTPS enabled
- ✅ Easy to update (just push changes)
- ✅ Version control included

**Cons:**
- ❌ Public repository only (unless Pro account)
- ❌ Static sites only

---

### Option 2: Netlify (Best for Easy Deployment)

**Steps:**

1. **Via Drag & Drop**
   - Go to [netlify.com](https://netlify.com)
   - Sign up/Login
   - Drag the entire `sharan-portfolio-resume` folder
   - Site goes live instantly!

2. **Via CLI**
   ```bash
   # Install Netlify CLI
   npm install -g netlify-cli

   # Deploy
   cd /Users/sharan.j/sharan-portfolio-resume
   netlify deploy

   # Follow prompts
   # For production: netlify deploy --prod
   ```

3. **Via Git**
   - Connect your GitHub repository
   - Automatic deployments on push
   - Preview deployments for pull requests

**Pros:**
- ✅ Instant deployment
- ✅ Custom domain support
- ✅ HTTPS automatic
- ✅ Continuous deployment
- ✅ Built-in analytics
- ✅ Form handling support
- ✅ Free tier generous

**Cons:**
- ❌ Build minutes limited on free tier

---

### Option 3: Vercel (Best for Modern Workflow)

**Steps:**

1. **Via CLI**
   ```bash
   # Install Vercel CLI
   npm install -g vercel

   # Deploy
   cd /Users/sharan.j/sharan-portfolio-resume
   vercel
   
   # Follow prompts
   # For production: vercel --prod
   ```

2. **Via Git**
   - Import GitHub repository at [vercel.com](https://vercel.com)
   - Automatic deployments
   - Preview URLs for branches

**Pros:**
- ✅ Lightning fast CDN
- ✅ Automatic HTTPS
- ✅ Custom domains
- ✅ Preview deployments
- ✅ Edge functions support
- ✅ Analytics included

**Cons:**
- ❌ Bandwidth limits on free tier

---

### Option 4: Firebase Hosting

**Steps:**

1. **Install Firebase CLI**
   ```bash
   npm install -g firebase-tools
   ```

2. **Initialize Firebase**
   ```bash
   cd /Users/sharan.j/sharan-portfolio-resume
   firebase login
   firebase init hosting
   ```

3. **Configure**
   - Select existing project or create new
   - Set public directory to current folder (.)
   - Configure as single-page app: No
   - Don't overwrite index.html

4. **Deploy**
   ```bash
   firebase deploy
   ```

**Pros:**
- ✅ Google's global CDN
- ✅ Fast performance
- ✅ Custom domain support
- ✅ Free SSL
- ✅ Generous free tier

**Cons:**
- ❌ Requires Firebase account
- ❌ More complex setup

---

### Option 5: Render (Alternative Free Hosting)

**Steps:**

1. **Via Dashboard**
   - Go to [render.com](https://render.com)
   - Click "New +"
   - Select "Static Site"
   - Connect GitHub repository
   - Deploy

**Pros:**
- ✅ Free static site hosting
- ✅ Custom domains
- ✅ Automatic HTTPS
- ✅ Git integration

**Cons:**
- ❌ Slower than some alternatives

---

## Custom Domain Setup

### For GitHub Pages

1. Buy domain from provider (Namecheap, GoDaddy, etc.)
2. Add DNS records:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153
   Value: 185.199.109.153
   Value: 185.199.110.153
   Value: 185.199.111.153
   
   Type: CNAME
   Name: www
   Value: sharanakash.github.io
   ```
3. Add CNAME file to repository:
   ```bash
   echo "yourdomain.com" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

### For Netlify/Vercel

1. Go to domain settings in dashboard
2. Add custom domain
3. Update DNS records with provided values
4. Wait for SSL to provision (automatic)

---

## Pre-Deployment Checklist

### ✅ Content Review
- [ ] All personal information is correct
- [ ] Email and phone numbers are accurate
- [ ] GitHub profile link works
- [ ] All project descriptions are complete
- [ ] No placeholder text remaining

### ✅ Technical Checks
- [ ] All links work (internal and external)
- [ ] Contact form submits correctly
- [ ] Images load properly
- [ ] No console errors
- [ ] Responsive on all devices
- [ ] Cross-browser testing complete

### ✅ SEO Optimization
- [ ] Add meta descriptions
- [ ] Add Open Graph tags
- [ ] Add Twitter Card tags
- [ ] Create favicon
- [ ] Add robots.txt
- [ ] Create sitemap.xml

### ✅ Performance
- [ ] Images optimized
- [ ] CSS minified (optional)
- [ ] JavaScript minified (optional)
- [ ] Lighthouse score > 90

### ✅ Accessibility
- [ ] Alt text for images
- [ ] Proper heading hierarchy
- [ ] Color contrast meets WCAG standards
- [ ] Keyboard navigation works
- [ ] Screen reader friendly

---

## SEO Enhancements

Add these meta tags to `<head>` section in index.html:

```html
<!-- SEO Meta Tags -->
<meta name="description" content="Sharan J S - Software Test Engineer with 3+ years of experience in test automation, microservices testing, and AI-powered development. Specialized in Selenium, Playwright, and BDD Cucumber.">
<meta name="keywords" content="SDET, Test Automation, Selenium, Playwright, Software Testing, QA Engineer, Microservices Testing">
<meta name="author" content="Sharan J S">
<meta name="robots" content="index, follow">

<!-- Open Graph / Facebook -->
<meta property="og:type" content="website">
<meta property="og:url" content="https://yourdomain.com/">
<meta property="og:title" content="Sharan J S - Software Test Engineer Portfolio">
<meta property="og:description" content="Experienced SDET specializing in test automation and microservices testing. 85-92% reduction in testing time through intelligent automation.">
<meta property="og:image" content="https://yourdomain.com/preview-image.jpg">

<!-- Twitter -->
<meta property="twitter:card" content="summary_large_image">
<meta property="twitter:url" content="https://yourdomain.com/">
<meta property="twitter:title" content="Sharan J S - Software Test Engineer Portfolio">
<meta property="twitter:description" content="Experienced SDET specializing in test automation and microservices testing.">
<meta property="twitter:image" content="https://yourdomain.com/preview-image.jpg">

<!-- Favicon -->
<link rel="icon" type="image/x-icon" href="/favicon.ico">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
```

---

## Create Favicon

1. **Generate Favicon**
   - Use [favicon.io](https://favicon.io) or [realfavicongenerator.net](https://realfavicongenerator.net)
   - Upload logo or create text-based icon
   - Download favicon package

2. **Add to Project**
   ```bash
   # Place favicon files in root directory
   favicon.ico
   apple-touch-icon.png
   favicon-16x16.png
   favicon-32x32.png
   ```

---

## Analytics Setup

### Google Analytics

1. Create account at [analytics.google.com](https://analytics.google.com)
2. Get tracking ID
3. Add to `<head>` of index.html:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

---

## Continuous Deployment Workflow

1. **Make Changes Locally**
   ```bash
   # Edit files
   git add .
   git commit -m "Update: [description]"
   git push
   ```

2. **Automatic Deployment**
   - GitHub Pages: Redeploys automatically
   - Netlify/Vercel: Builds and deploys on push
   - Firebase: Manual deploy required

3. **Preview Changes**
   - Use branch previews on Netlify/Vercel
   - Test before merging to main

---

## Monitoring & Maintenance

### Performance Monitoring
- Google PageSpeed Insights
- Lighthouse CI
- WebPageTest
- GTmetrix

### Uptime Monitoring
- UptimeRobot (free)
- Pingdom
- StatusCake

### Regular Updates
- Update content quarterly
- Add new projects
- Update skills
- Refresh achievements
- Check all links monthly

---

## Troubleshooting

### Site Not Loading
1. Check DNS settings
2. Verify deployment logs
3. Clear browser cache
4. Check SSL certificate status

### Broken Links
1. Use broken link checker
2. Update all URLs
3. Test thoroughly before deployment

### Slow Loading
1. Optimize images
2. Minify CSS/JS
3. Enable caching
4. Use CDN

---

## Next Steps After Deployment

1. ✅ Test live site on all devices
2. ✅ Set up analytics
3. ✅ Submit to Google Search Console
4. ✅ Share on LinkedIn, Twitter
5. ✅ Add to resume/CV
6. ✅ Monitor performance
7. ✅ Gather feedback
8. ✅ Iterate and improve

---

## Support & Resources

- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [Netlify Docs](https://docs.netlify.com)
- [Vercel Docs](https://vercel.com/docs)
- [Firebase Docs](https://firebase.google.com/docs/hosting)

---

**Good luck with your deployment! 🚀**
