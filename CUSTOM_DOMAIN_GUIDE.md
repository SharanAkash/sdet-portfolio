# 🌐 Custom Domain Setup Guide

## Current URLs:
- ❌ https://main.d11ql67lvu8pr0.amplifyapp.com (Too long)
- ✅ Custom domain like: `sharanjs.com` (Professional!)

---

## 🎯 Option 1: Buy Custom Domain (Recommended)

### **Suggested Domain Names:**
1. `sharanjs.com` ⭐ (Best - Your name)
2. `sharanjs.dev` (For developers)
3. `sdetportfolio.com` (Descriptive)
4. `sharanjssdet.com` (Name + Role)
5. `sharan-qa.com` (Short)

### **Where to Buy (Cheap & Reliable):**

**1. Namecheap** (Recommended - Cheapest)
   - Website: https://www.namecheap.com
   - Cost: $8-12/year (.com)
   - Cost: $3-5/year (.dev)
   - Easy DNS management
   - Free WHOIS privacy

**2. GoDaddy**
   - Website: https://www.godaddy.com
   - Cost: $10-15/year
   - Good support

**3. Google Domains** (Now Squarespace Domains)
   - Website: https://domains.google
   - Cost: $12/year
   - Simple interface

**4. Cloudflare Domains**
   - Website: https://www.cloudflare.com/products/registrar/
   - Cost: At-cost pricing
   - Free SSL & CDN

**5. AWS Route 53** (If staying in AWS)
   - Cost: $12/year + $0.50/month hosting
   - Fully integrated with AWS

---

## 🚀 Setup Steps for Custom Domain with AWS Amplify:

### **Step 1: Buy Domain**
```bash
# Example: Buy sharanjs.com from Namecheap
# Cost: ~$10/year
```

### **Step 2: Add Domain to AWS Amplify**

**Via AWS Console (Easy):**
1. Go to AWS Amplify Console
2. Select your app: `sdet-portfolio`
3. Click "Domain management"
4. Click "Add domain"
5. Enter your domain: `sharanjs.com`
6. Follow verification steps

**Via AWS CLI:**
```bash
aws amplify create-domain-association \
  --app-id d11ql67lvu8pr0 \
  --domain-name sharanjs.com \
  --enable-auto-sub-domain \
  --sub-domain-settings prefix=www,branchName=main \
  --region us-east-1
```

### **Step 3: Update DNS Records**

AWS Amplify will provide DNS records. Add these to your domain provider:

**Example DNS Records:**
```
Type: CNAME
Name: www
Value: <amplify-provided-value>

Type: A
Name: @
Value: <amplify-provided-ip>
```

### **Step 4: Wait for Verification**
- DNS propagation: 1-48 hours
- SSL certificate: Auto-provisioned by AWS
- Status: Check in Amplify Console

### **Step 5: Done!**
Your portfolio will be accessible at:
- `https://sharanjs.com` ✅
- `https://www.sharanjs.com` ✅

---

## 💰 Cost Breakdown:

### **Domain Purchase:**
- `.com` domain: $10-15/year
- `.dev` domain: $12-15/year
- `.me` domain: $10-20/year
- `.tech` domain: $15-25/year

### **AWS Amplify:**
- First year: FREE (Free tier)
- After: $1-5/month (very cheap)

### **Total First Year:**
- Domain: $12
- Amplify: $0 (free tier)
- **Total: ~$12/year** 🎉

### **Total After First Year:**
- Domain: $12/year
- Amplify: ~$24/year ($2/month)
- **Total: ~$36/year** ($3/month)

---

## 🎯 Option 2: Use GitHub Pages Custom Domain (Free!)

If you want to save money, use GitHub Pages with custom domain:

### **Steps:**
1. Buy domain (same as above)
2. Go to GitHub repository settings
3. Add custom domain
4. Update DNS records to point to GitHub

### **DNS Records for GitHub:**
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

### **Cost:**
- Domain: $10-15/year
- GitHub Pages: FREE ✅
- **Total: ~$12/year**

---

## 🎯 Option 3: Free Short URL (No Custom Domain)

If you don't want to buy a domain yet:

### **1. Bitly**
```bash
# Create account: https://bitly.com
# Shorten: https://main.d11ql67lvu8pr0.amplifyapp.com
# Get: https://bit.ly/sharanjs-portfolio
```

### **2. TinyURL**
```
https://tinyurl.com
Create: https://tinyurl.com/sharanjs
```

### **3. Is.gd**
```
https://is.gd
Create: https://is.gd/sharanjs
```

**Pros:**
- ✅ Free
- ✅ Instant
- ✅ Shorter URL

**Cons:**
- ❌ Not professional
- ❌ No brand control
- ❌ Can expire

---

## 🎯 Option 4: Free Subdomain Services

### **1. Vercel (Free)**
```bash
# Deploy to Vercel
vercel --prod

# Get: https://sdet-portfolio.vercel.app
# Free, clean, professional!
```

### **2. Netlify (Free)**
```bash
# Deploy to Netlify
netlify deploy --prod

# Get: https://sharanjs-sdet.netlify.app
# Can customize subdomain name!
```

**Cost: FREE** ✅

---

## 📋 Comparison Table:

| Option | URL Example | Cost/Year | Professional | Setup Time |
|--------|-------------|-----------|--------------|------------|
| Custom Domain + Amplify | sharanjs.com | $36 | ⭐⭐⭐⭐⭐ | 2-48 hours |
| Custom Domain + GitHub | sharanjs.com | $12 | ⭐⭐⭐⭐⭐ | 2-48 hours |
| Vercel Free | project.vercel.app | $0 | ⭐⭐⭐⭐ | 5 minutes |
| Netlify Free | project.netlify.app | $0 | ⭐⭐⭐⭐ | 5 minutes |
| Bitly Short URL | bit.ly/sharanjs | $0 | ⭐⭐ | 2 minutes |
| Current Amplify | main.d11q...app.com | $0-5 | ⭐⭐⭐ | Done! |

---

## 🌟 My Recommendation:

### **For Beginners (FREE):**
Deploy to **Netlify** for cleaner URL:
- Free subdomain: `sharanjs-portfolio.netlify.app`
- Better than current URL
- Still professional
- Takes 5 minutes

### **For Professionals ($12/year):**
Buy `sharanjs.com` and use GitHub Pages:
- Most professional
- Your own brand
- Very cheap
- Full control

### **For Best Experience ($36/year):**
Buy `sharanjs.com` and use AWS Amplify:
- Most professional
- Best performance (CDN)
- Auto-deploy from GitHub
- Full AWS features

---

## 🚀 Quick Setup: Netlify (5 Minutes - FREE)

### **Step 1: Install Netlify CLI**
```bash
npm install -g netlify-cli
```

### **Step 2: Login**
```bash
netlify login
```

### **Step 3: Deploy**
```bash
cd /Users/sharan.j/sharan-portfolio-resume
netlify deploy --prod
```

### **Step 4: Choose Site Name**
When prompted, choose: `sharanjs-sdet`
Result: `https://sharanjs-sdet.netlify.app`

**Done!** 🎉

---

## 🛠️ How to Buy Domain (Step by Step):

### **Namecheap Example:**

1. **Go to Namecheap:**
   - https://www.namecheap.com

2. **Search for Domain:**
   - Search: `sharanjs`
   - Check availability

3. **Add to Cart:**
   - Select `.com` ($10/year)
   - Add to cart

4. **Checkout:**
   - Create account
   - Pay with card/PayPal
   - Enable WHOIS privacy (FREE)

5. **Configure DNS:**
   - Go to dashboard
   - Select domain
   - Manage DNS
   - Add records (provided by Amplify/GitHub)

6. **Wait:**
   - DNS propagation: 1-48 hours
   - Check: https://sharanjs.com

**Total Time:** 30 minutes + DNS wait

---

## 🔍 Domain Name Tips:

### **Good Domain Names:**
✅ Short (under 15 characters)
✅ Easy to spell
✅ Easy to remember
✅ No hyphens or numbers
✅ .com extension (most trusted)
✅ Your name or brand

### **Examples:**
- ✅ sharanjs.com (Best!)
- ✅ sharanj.dev
- ✅ sharan.tech
- ❌ sharan-j-s-portfolio-2024.com (Too long)
- ❌ sdet123.com (Numbers)

---

## 🎯 Immediate Action Plan:

### **Option A: Free (Right Now):**
```bash
# Deploy to Netlify for better URL
npm install -g netlify-cli
netlify login
cd /Users/sharan.j/sharan-portfolio-resume
netlify deploy --prod
# Choose name: sharanjs-sdet
```
**Result:** `https://sharanjs-sdet.netlify.app`

### **Option B: Paid ($12) - This Weekend:**
1. Go to Namecheap.com
2. Buy `sharanjs.com` ($10)
3. Add to GitHub Pages or Amplify
4. Configure DNS
5. Wait 24-48 hours

**Result:** `https://sharanjs.com`

---

## 📞 Need Help?

**I can help you:**
1. Deploy to Netlify right now (FREE)
2. Configure custom domain with Amplify
3. Set up GitHub Pages with custom domain
4. Choose the best domain name

**Just let me know which option you prefer!**

---

## ✅ Summary:

**Current URL:**
- https://main.d11ql67lvu8pr0.amplifyapp.com

**Better FREE Options:**
- Netlify: `sharanjs-sdet.netlify.app`
- Vercel: `sharanjs-sdet.vercel.app`

**Best Professional Option:**
- Custom Domain: `sharanjs.com` ($12/year)

**Recommendation:**
Start with Netlify (FREE), then buy custom domain later!

---

**Let me know which option you want, and I'll help you set it up!** 🚀
