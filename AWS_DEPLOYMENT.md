# AWS Deployment - Complete ✅

## 🚀 Your Portfolio is LIVE!

### Deployment Details:

**AWS Account**: 637423656090 (Sharan J S)  
**Service**: Amazon S3 + Static Website Hosting  
**Bucket Name**: sdet-portfolio-sharanjs  
**Region**: us-east-1 (US East - N. Virginia)

---

## 🌐 Live URLs:

### **Primary URL (S3 Website)**
```
http://sdet-portfolio-sharanjs.s3-website-us-east-1.amazonaws.com
```

### **GitHub Pages URL** (Already Live)
```
https://sharanakash.github.io/sdet-portfolio/
```

### **GitHub Repository**
```
https://github.com/SharanAkash/sdet-portfolio
```

---

## 📦 What Was Deployed:

✅ index.html - Main portfolio page  
✅ styles.css - Styling and animations  
✅ script.js - Interactive features  
✅ Sharan_J_S_Resume.pdf - Resume download  
✅ All images and assets  

---

## 🔧 AWS Configuration:

### S3 Bucket Settings:
- **Static Website Hosting**: Enabled
- **Index Document**: index.html
- **Error Document**: index.html (for SPA routing)
- **Public Access**: Enabled
- **Bucket Policy**: Public read access
- **Cache Control**: 1 hour (3600 seconds)

### Security:
- Bucket policy allows public read access
- HTTPS available via CloudFront (optional upgrade)

---

## 🔄 How to Update Your Portfolio:

### Method 1: Quick Update (Recommended)
```bash
cd /Users/sharan.j/sharan-portfolio-resume

# Make your changes to files, then:
git add .
git commit -m "Update: describe your changes"
git push origin main

# Upload to AWS S3
aws s3 sync . s3://sdet-portfolio-sharanjs \
  --exclude ".git/*" \
  --exclude ".gitignore" \
  --exclude "*.md" \
  --exclude "*.txt" \
  --exclude ".claude/*" \
  --cache-control "max-age=3600"
```

### Method 2: Single File Update
```bash
# Update a single file
aws s3 cp index.html s3://sdet-portfolio-sharanjs/index.html

# Update CSS
aws s3 cp styles.css s3://sdet-portfolio-sharanjs/styles.css

# Update JavaScript
aws s3 cp script.js s3://sdet-portfolio-sharanjs/script.js
```

### Method 3: Update Resume Only
```bash
aws s3 cp Sharan_J_S_Resume.pdf s3://sdet-portfolio-sharanjs/Sharan_J_S_Resume.pdf
```

---

## 🌟 Optional Upgrades:

### 1. Add CloudFront CDN (Faster + HTTPS)
```bash
# Create CloudFront distribution
aws cloudfront create-distribution \
  --origin-domain-name sdet-portfolio-sharanjs.s3.amazonaws.com \
  --default-root-object index.html
```

**Benefits:**
- ✅ HTTPS support (secure connection)
- ✅ Faster global loading (CDN caching)
- ✅ Custom domain support
- ✅ Better performance

### 2. Add Custom Domain
1. Buy domain (e.g., sharanjs.com)
2. Configure Route 53 DNS
3. Point to CloudFront or S3
4. Add SSL certificate (free with AWS Certificate Manager)

### 3. Enable Versioning
```bash
aws s3api put-bucket-versioning \
  --bucket sdet-portfolio-sharanjs \
  --versioning-configuration Status=Enabled
```

---

## 📊 Monitoring & Analytics:

### Check Website Status:
```bash
curl -I http://sdet-portfolio-sharanjs.s3-website-us-east-1.amazonaws.com
```

### View Bucket Contents:
```bash
aws s3 ls s3://sdet-portfolio-sharanjs/
```

### Check Access Logs (if enabled):
```bash
aws s3api get-bucket-logging --bucket sdet-portfolio-sharanjs
```

---

## 💰 Cost Estimate:

**Monthly Cost**: ~$0.50 - $2.00 USD

- S3 Storage: ~0.20 MB = $0.005/month
- S3 Requests: First 2,000 GET requests free
- Data Transfer: First 1 GB free, then $0.09/GB
- **Expected**: Less than $1/month for moderate traffic

**Free Tier**: First 12 months includes 5GB storage + 20,000 GET requests

---

## 🛠️ Troubleshooting:

### Site Not Loading?
```bash
# Check bucket policy
aws s3api get-bucket-policy --bucket sdet-portfolio-sharanjs

# Check website configuration
aws s3api get-bucket-website --bucket sdet-portfolio-sharanjs

# Re-upload files
aws s3 sync . s3://sdet-portfolio-sharanjs --exclude ".git/*"
```

### Permission Denied?
```bash
# Re-apply public access
aws s3api put-bucket-policy --bucket sdet-portfolio-sharanjs --policy file:///tmp/bucket-policy.json
```

### Need to Delete and Redeploy?
```bash
# Delete all files
aws s3 rm s3://sdet-portfolio-sharanjs --recursive

# Re-upload
aws s3 sync . s3://sdet-portfolio-sharanjs --exclude ".git/*"
```

---

## 📱 Share Your Portfolio:

✅ **LinkedIn**: Add to your profile experience section  
✅ **Resume**: Add URL to your resume  
✅ **Email Signature**: Include portfolio link  
✅ **GitHub README**: Add link to your GitHub profile  
✅ **Job Applications**: Include in cover letters  

---

## 🔐 Security Best Practices:

1. ✅ Never commit sensitive data (API keys, passwords)
2. ✅ Keep resume PDF updated
3. ✅ Monitor AWS billing dashboard
4. ✅ Enable MFA on AWS account
5. ✅ Use IAM roles instead of root credentials

---

## 📞 Support & Resources:

- **AWS S3 Documentation**: https://docs.aws.amazon.com/s3/
- **AWS Cost Calculator**: https://calculator.aws/
- **AWS Free Tier**: https://aws.amazon.com/free/
- **GitHub Docs**: https://docs.github.com/

---

## ✅ Deployment Summary:

- ✅ GitHub Repository Created: https://github.com/SharanAkash/sdet-portfolio
- ✅ GitHub Pages Enabled: https://sharanakash.github.io/sdet-portfolio/
- ✅ AWS S3 Bucket Created: sdet-portfolio-sharanjs
- ✅ Static Website Hosting Enabled
- ✅ Files Uploaded Successfully
- ✅ Public Access Configured
- ✅ Portfolio is LIVE and accessible worldwide!

---

**Deployed on**: June 30, 2026  
**By**: Claude Code + Sharan J S  
**Status**: ✅ Production Ready

🎉 **Congratulations! Your portfolio is now live on AWS!** 🎉
