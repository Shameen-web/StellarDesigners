# Stellar Design Studio - AWS S3 Static Website with IAM Security

## Project Overview

This project demonstrates a **scalable static website solution** hosted on AWS S3 with **secure access control** implemented using IAM (Identity and Access Management).

### Live Website
🌐 **Website URL:** 🌐 [Live Website: Stellar Design Studio](http://stellar-design-studio.s3-website-us-east-1.amazonaws.com)

## Architecture & Technologies Used

### **1. AWS S3 (Simple Storage Service)**
- Hosts the static website (HTML, CSS, JavaScript)
- Bucket name: `stellar-design-studio`
- Region: `us-east-1`
- Configured for static website hosting with index document: `index.html`

### **2. AWS IAM (Identity and Access Management)**
- Manages user access and permissions
- Implements least-privilege access control
- Secure credential management

### **3. Website**
- **Framework:** Pure HTML5 + CSS3 (no dependencies)
- **Type:** Static website (no backend/database)
- **Design:** Modern responsive design with gradient UI, animations, and interactive elements

---

## Project Components

### **Website Features**
✨ Modern gradient design with purple-to-pink color scheme  
🎨 Smooth animations and hover effects  
📱 Fully responsive (mobile, tablet, desktop)  
🔗 Navigation menu with smooth scrolling  
📊 Service showcase section (6 services)  
🖼️ Portfolio section (3 featured projects)  
📝 About section with statistics  
📧 Contact form  
🎯 Call-to-action button

### **IAM Security Setup**

#### **IAM Users Created:**
1. **Designer** - Full S3 access (can upload, delete, manage files)
2. **Viewer** - Read-only S3 access (can only view files)

#### **IAM Groups Created:**
1. **Designers Group** - Attached policy: `AmazonS3FullAccess`
2. **Viewers Group** - Attached policy: `AmazonS3ReadOnlyAccess`

#### **Security Policy:**
- S3 Bucket Policy: Allows public read access to all files
- IAM Policies: Restrict upload/delete operations to Designer users only
- Principle of Least Privilege: Each user has minimum required permissions

---

## Security Testing Results

### **Test 1: Designer User Upload**
✅ **Result:** SUCCESS  
- Designer user can upload files to S3 bucket
- Verified by uploading `test-designer.txt` successfully

### **Test 2: Viewer User Upload (Permission Denied)**
✅ **Result:** BLOCKED (as intended)  
- Viewer user attempted to upload file
- Error: "Access Denied" - Upload failed
- Proves read-only access is working correctly

**Conclusion:** IAM security is functioning as designed. Only authorized users (Designer) can modify bucket contents.

---

## How It Works

### **S3 Hosting Flow:**
1. Website files (`index.html` + assets) stored in S3 bucket
2. S3 configured for static website hosting
3. Bucket policy allows public read access
4. Website accessible via S3 endpoint URL
5. Automatically scales for traffic (no server management needed)

### **IAM Access Control Flow:**
1. Users authenticate with credentials (username + password)
2. IAM checks user's group membership
3. Group's attached policies determine permissions
4. S3 operations allowed/denied based on policy
5. CloudTrail logs all access attempts (for audit trail)

---

## Key Learnings

✅ **AWS S3:** How to host static websites without managing servers  
✅ **Scalability:** S3 automatically handles traffic spikes  
✅ **IAM Users:** Creating virtual user accounts with AWS credentials  
✅ **IAM Groups:** Managing permissions for teams efficiently  
✅ **IAM Policies:** Writing and attaching security policies  
✅ **Principle of Least Privilege:** Giving users only minimum required permissions  
✅ **Security Testing:** Verifying access control works correctly  
✅ **Bucket Policies:** Making resources publicly accessible securely  

## screenshots 
Available in Screenshots folders 
