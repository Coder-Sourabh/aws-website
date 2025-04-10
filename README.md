# Static Website Deployment on AWS S3 using GitHub Actions

This project demonstrates how to host a static website on **AWS S3** with automated deployment using **GitHub Actions**. Any code pushed from **VS Code** to the GitHub repository triggers a workflow that builds and deploys the website to S3. The site is publicly accessible via the S3 static website hosting feature.

## 🛠 Tech Stack
- **VS Code** – Code editor
- **GitHub** – Source code hosting
- **GitHub Actions** – CI/CD automation
- **AWS S3** – Static website hosting
- **AWS IAM** – Public access configuration

## 🚀 Workflow

1. Code is written and pushed from **VS Code** to **GitHub**.
2. **GitHub Actions** triggers on push to the main branch.
3. The workflow builds the site (if needed) and deploys it to **AWS S3**.
4. The website is accessible to all users via public S3 static hosting.

## 🔐 IAM Permissions
The S3 bucket policy is configured to allow public read access for all users. Example policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
