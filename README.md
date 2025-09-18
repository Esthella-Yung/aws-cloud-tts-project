
# 🎙️ AWS Text-to-Speech Application  

This project is a **serverless web application** that converts text into speech using AWS services.  
The entire infrastructure was fully provisioned using **Terraform**.  

---

## ✨ Features  
- Convert text to **natural-sounding speech** with **Amazon Polly**  
- Store generated audio files securely in **Amazon S3**  
- Trigger text-to-speech via **AWS Lambda** and **API Gateway**  
- Simple **HTML/JavaScript frontend** hosted on **S3**  
- Secure architecture with **IAM least privilege** and **pre-signed URLs**  
- Fully automated deployment using **Terraform**  

---

## ☁️ AWS Services Used  
- **Amazon S3** – static website hosting & audio storage  
- **Amazon API Gateway** – public entry point for backend  
- **AWS Lambda** – serverless backend logic  
- **Amazon Polly** – text-to-speech conversion  
- **IAM** – fine-grained access control  
- **Terraform** – infrastructure as code  

---

## 🏗️ Architecture Diagram  

```<img width="611" height="587" alt="text-speech drawio" src="https://github.com/user-attachments/assets/54ed3283-4ee2-4ba5-82fc-a45ae8015bc9" />

flowchart TD
    User -->|Enter text| Frontend[S3 Static Website]
    Frontend -->|API Call| APIGateway[Amazon API Gateway]
    APIGateway -->|Invoke| Lambda[AWS Lambda]
    Lambda --> Polly[Amazon Polly]
    Polly -->|Audio File| S3Bucket[Amazon S3 Bucket]
    S3Bucket -->|Pre-signed URL| Frontend
````

---

## 📂 Project Structure

```
text-speech-app/
│── main.tf              # Terraform root config
│── providers.tf         # Provider definitions
│── iam.tf               # IAM roles & policies
│── lambda.tf            # Lambda function setup
│── api_gateway.tf       # API Gateway config
│── s3.tf                # S3 buckets & hosting
│── outputs.tf           # Useful Terraform outputs
│── frontend/
│    ├── index.html      # Web UI
│    ├── script.js       # API calls & audio playback
```

---

## ⚡ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Esthella-Yung/aws-cloud-tts-project.git
```

### 2. Deploy Infrastructure with Terraform

```bash
terraform init
terraform plan
terraform apply
```

> Ensure your **AWS CLI** is configured with appropriate credentials.

### 3. Upload Frontend to S3

```bash
aws s3 sync frontend/ s3://<https://static-website-bucket10-79c19550.s3.us-east-1.amazonaws.com/index.html>
```

### 4. Test the Application

* Open the **S3 website URL** from Terraform outputs.
* Enter some text → Click **Convert** → Listen to generated audio 🎧

---

## 🔒 Security Considerations

* Used **IAM least privilege** for Lambda & API Gateway
* Implemented **CORS** for frontend-backend communication
* Audio files accessed via **pre-signed S3 URLs** (temporary, secure access)

---

## 📈 Future Improvements

* Add **user authentication** with AWS Cognito
* Support **multiple voices and languages** in frontend
* Implement **CI/CD** with AWS CodePipeline
* Add **monitoring dashboards** with CloudWatch Metrics

---

## 🧑‍💻 Author

Developed by **Esthella Rahama Abdul Wahab**

💼 [LinkedIn Profile](https://www.linkedin.com/in/esthella-rahama-abdul-wahab)

---

## 📜 License

This project is licensed under the **MIT License**.

```

---

✨ This version will look **clean and well-structured** on GitHub, with proper headings, lists, and even a **Mermaid diagram** for your architecture.  

Do you also want me to **add badges** (Terraform, AWS, GitHub Actions) at the top to make it look more professional?
```
