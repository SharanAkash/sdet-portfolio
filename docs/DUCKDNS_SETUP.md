# 🦆 DuckDNS Domain Setup Guide

## Your Domain: jstamilcenima.duckdns.org

---

## 🎯 Setup Instructions:

### **Step 1: Update DuckDNS to Point to Your Portfolio**

You need to point your DuckDNS domain to your AWS hosting. We have 2 options:

---

### **Option 1: Point to AWS Amplify (Recommended - HTTPS)**

Since AWS Amplify uses CloudFront (dynamic IPs), we need to use a CNAME approach.

**Problem:** DuckDNS doesn't support CNAME for root domain.

**Solution:** Use AWS CloudFront or configure reverse proxy.

---

### **Option 2: Point to S3 Website (Simple - HTTP)**

**S3 Website URL:** 
```
http://sdet-portfolio-sharanjs.s3-website-us-east-1.amazonaws.com
```

**S3 IP Address:**
We need to get the IP of the S3 website endpoint.

---

### **Option 3: Use Cloudflare Pages (Best Solution!)**

Since DuckDNS has limitations with HTTPS, let me recommend using Cloudflare Pages:

1. **Deploy to Cloudflare Pages** (Free + HTTPS)
2. **Add custom domain:** `jstamilcenima.duckdns.org`
3. **Cloudflare handles HTTPS automatically**

---

## 🚀 Recommended Approach: Deploy to Cloudflare Pages

### **Why Cloudflare Pages?**
✅ Free hosting
✅ HTTPS support
✅ Works with DuckDNS
✅ Fast CDN
✅ Auto-deploy from GitHub
✅ Better than DuckDNS limitations

### **Steps:**

1. **Create Cloudflare Account:**
   - Go to: https://dash.cloudflare.com/sign-up
   - Sign up (FREE)

2. **Deploy to Cloudflare Pages:**
   - Go to: https://dash.cloudflare.com/pages
   - Click "Create a project"
   - Connect GitHub: `SharanAkash/sdet-portfolio`
   - Deploy

3. **Get Cloudflare Pages URL:**
   - You'll get: `sdet-portfolio.pages.dev`

4. **Update DuckDNS:**
   - Go to: https://www.duckdns.org
   - Login
   - Update `jstamilcenima` to point to Cloudflare IP
   - Or use CNAME to `sdet-portfolio.pages.dev`

---

## 🔧 Alternative: Simple HTTP Setup with DuckDNS

If you want to keep it simple (HTTP only):

### **Step 1: Get S3 Website IP**
```bash
nslookup sdet-portfolio-sharanjs.s3-website-us-east-1.amazonaws.com
```

### **Step 2: Update DuckDNS**
1. Go to: https://www.duckdns.org
2. Login with your account
3. Find domain: `jstamilcenima`
4. Update IP to S3 IP address
5. Click "update"

### **Step 3: Test**
```
http://jstamilcenima.duckdns.org
```

**Note:** This will be HTTP only (not secure).

---

## ⚠️ DuckDNS Limitations:

1. **No HTTPS Support:** DuckDNS doesn't provide SSL certificates
2. **No CNAME Support:** Can't directly point to Amplify
3. **Dynamic DNS:** Designed for home servers, not web hosting

---

## 🎯 Best Solution: Use Cloudflare

### **Quick Setup (10 minutes):**

1. **Deploy to Cloudflare Pages:**
   ```bash
   # Install Wrangler CLI
   npm install -g wrangler
   
   # Login
   wrangler login
   
   # Deploy
   cd /Users/sharan.j/sharan-portfolio-resume
   wrangler pages deploy . --project-name=sdet-portfolio
   ```

2. **Get URL:**
   - Cloudflare gives you: `sdet-portfolio.pages.dev`
   - HTTPS enabled automatically!

3. **Optional: Use DuckDNS as redirect:**
   - Point DuckDNS to Cloudflare
   - Or keep Cloudflare URL directly

---

## 📋 Comparison:

| Option | URL | HTTPS | Setup |
|--------|-----|-------|-------|
| Current Amplify | main.d11ql67lvu8pr0.amplifyapp.com | ✅ | Done |
| DuckDNS + S3 | jstamilcenima.duckdns.org | ❌ | 5 min |
| Cloudflare Pages | sdet-portfolio.pages.dev | ✅ | 10 min |
| DuckDNS + Cloudflare | jstamilcenima.duckdns.org | ✅ | 15 min |

---

## 🚀 Immediate Action:

Let me help you choose:

**Option A: Keep HTTPS (Recommended)**
- Use current Amplify URL
- Or deploy to Cloudflare Pages
- Professional and secure

**Option B: Use DuckDNS (HTTP only)**
- Point to S3 website
- No HTTPS (not recommended for portfolio)
- Easy but unprofessional

**Option C: Hybrid**
- Deploy to Cloudflare Pages
- Use DuckDNS as secondary URL
- Best of both worlds

---

**What would you like to do?**

1. Keep current HTTPS URL (best for now)
2. Setup HTTP with DuckDNS (quick but not secure)
3. Deploy to Cloudflare Pages (best long-term solution)

Let me know and I'll help you set it up!
