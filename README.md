# 🔐 BioVault – Secure Cloud Vault for Biometrics

**BioVault** is a secure, cloud-based Android application designed for storing, managing, and processing biometric images such as fingerphotos. Leveraging AWS services including Amplify, Lambda, S3, and Boto3, the project showcases a practical pipeline for secure biometric data handling, privacy-preserving uploads, and serverless processing. This system is built to support compliant, scalable deployment of biometric authentication tools in real-world mobile environments.


---

## 🔧 Technologies Used

- **Android (Kotlin/Java)** – Mobile interface for user interaction
- **AWS Amplify** – User authentication, API management, and S3 integration
- **AWS Lambda** – Serverless backend logic for photo processing
- **Amazon S3** – Secure cloud storage for user media
- **Boto3** – AWS SDK for Lambda-based S3 operations

---

## 📱 Features

- User sign-up/sign-in with Amazon Cognito
- Upload photos directly from camera or gallery
- View personal photo gallery (retrieved from S3)
- Secure photo deletion
- Optional image processing via Lambda (resize/filtering)

---

## 🧱 Architecture Overview

```
[ Android App ]
       ↓
[ AWS Amplify (Auth + API Gateway) ]
       ↓
[ AWS Lambda (Boto3 Processing) ]
       ↓
[ Amazon S3 (Secure Media Storage) ]
```

---

## 🚀 Getting Started

### Prerequisites
- Android Studio
- Amplify CLI (`npm install -g @aws-amplify/cli`)
- AWS account with IAM user configured

### Setup

1. **Initialize Amplify project**
   ```bash
   amplify init
   amplify add auth
   amplify add storage
   amplify add api
   amplify push
   ```

2. **Configure Android App**
   - Add Amplify dependencies in `build.gradle`
   - Initialize Amplify in `MainApplication`
   - Use `Amplify.Auth` and `Amplify.Storage` for user and file management

3. **Deploy Lambda Function**
   - Write a Lambda in Python using Boto3 to handle S3 logic
   - Connect via REST API or S3 triggers
   - Attach IAM permissions for S3 access

---

## 📁 Folder Structure

```
/android-app/         ← Android source code
/amplify/             ← Amplify backend config
/lambda/              ← Lambda function code
/README.md
```

---

## ✅ Example Use Case

- User logs into the app via Amplify Auth
- Selects or captures a photo and uploads it
- Amplify stores the photo in S3
- Lambda (optional) processes the image (e.g., resize)
- User sees an updated gallery of their images

---

## 🔐 Security

- S3 is private; access is granted only via signed URLs through Amplify
- No hardcoded credentials
- Supports AWS IAM roles and policies for fine-grained access control

---

## 📄 License

This project is provided for educational purposes and is not affiliated with or representative of any proprietary work. No confidential or internal tools or data are included.
