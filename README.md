## 🚀 Static Website Hosting using AWS S3 <br>

## 📌 Project Overview
This project demonstrates how to host a static website using AWS S3.

The website is deployed by uploading HTML, CSS, and JavaScript files directly to an S3 bucket and enabling static website hosting.

---

## 🧠 Architecture

<img width="805" height="442" alt="_- visual selection (10)" src="https://github.com/user-attachments/assets/3954b63e-7b53-42dc-9ed4-fbe6486e8d58" />

---

## 🛠️ Tools Used

- AWS S3
- HTML, CSS, JavaScript

---

## ⚙️ Setup Steps

### 1. Create S3 Bucket
- Created a globally unique S3 bucket
- Selected region (ap-south-1)
- Bucket acts as storage for static website files

### 2. Configure Public Access
- Disabled "Block all public access"
- Required to make website accessible over the internet

### 3. Enable Static Website Hosting
- Enabled static website hosting in bucket properties
- Configured:
  - index.html as index document
  - error.html as error document
  
### 4. Configure Bucket Policy
- Added policy to allow public read access to all objects

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

### 5. Upload Website Files
- Uploaded HTML, CSS, JavaScript, and image files to the S3 bucket
- Ensured correct file structure for proper rendering

### 6. Access the Website
- Used S3 static website endpoint URL
- Verified website accessibility in browser

### 7. Error Handling
- Configured custom error page (error.html)
- Handles invalid routes instead of default AWS error
----

## ⚠️ Limitations

- No HTTPS support (without CloudFront)
- Manual deployment required

---

## 🚀 Future Improvements

- Add CloudFront for HTTPS
- Automate deployment using Jenkins

---
