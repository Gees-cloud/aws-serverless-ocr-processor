# 🧾 Serverless OCR Document Processor with AWS

This project provides a *fully serverless Optical Character Recognition (OCR)* pipeline built entirely with AWS services and deployed using *CloudFormation. It automates the extraction of text from documents uploaded to an S3 bucket using **Amazon Textract, stores the extracted content in **DynamoDB, and delivers a summary of the results via email using **Amazon SES—all orchestrated through **AWS Lambda*.

This solution is ideal for anyone looking to build document automation workflows, enhance AI-driven processes, or explore practical serverless architectures on AWS.

---

## ✨ *Features*

- *Automated OCR:* Automatically extracts text from uploaded PDF, PNG, and JPG documents  
- *Scalable & Serverless:* Built on AWS Lambda and S3 for a pay-as-you-go architecture  
- *Persistent Storage:* Extracted text is stored in DynamoDB  
- *Email Notifications:* Sends results via Amazon SES  
- *Infrastructure as Code:* Entire stack deployed via CloudFormation  
- *Monitoring:* CloudWatch integrated for visibility

---

## 🚀 *Tech Stack*

- *Amazon S3* – for document storage and Lambda trigger  
- *AWS Lambda* – to process uploaded files  
- *Amazon Textract* – to extract text from images and PDFs  
- *Amazon DynamoDB* – for storing OCR results  
- *Amazon SES* – for emailing extracted text  
- *AWS CloudFormation* – to provision all services  
- *AWS CloudWatch* – for logging and monitoring

---

## 📂 *Project Structure*

. ├── template.yaml           # CloudFormation template defining the entire AWS stack └── README.md               # Project documentation and guide (this file)

---

## ⚙ *How It Works*

1. *Upload* a .pdf, .png, or .jpg to the input S3 bucket  
2. *S3 triggers* the Lambda function  
3. *Lambda calls* Textract to extract text  
4. *Stores* result in DynamoDB  
5. *Sends* email summary using SES  
6. *Logs* the process in CloudWatch

---

## 🔐 *Prerequisites*

- AWS account  
- AWS CLI configured  
- Verified email in *Amazon SES (sandbox mode)*  
- IAM permissions to deploy stack + create services

---

## 📦 *Deploy This Project*

1. *Clone the repo*  
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

2. Customize template.yaml if needed


3. Deploy via AWS CLI



aws cloudformation deploy \
  --template-file template.yaml \
  --stack-name Serverless-OCR-Processor \
  --capabilities CAPABILITY_NAMED_IAM \
  --parameter-overrides SenderEmail=you@example.com RecipientEmail=you@example.com

4. Upload a test file (PDF/PNG/JPG) to the S3 bucket from CloudFormation Output


5. Check your inbox! — You'll receive an email with extracted text from Textract


---

📸 Screenshots (Project in Action) 


![S3 real world project](https://github.com/user-attachments/assets/c20d4bae-ab88-4cb6-9fda-e8eaf1b07f74)

✅ Lambda Triggered (CloudWatch Logs)  

![cloudwatch 1](https://github.com/user-attachments/assets/5416f14d-1b49-47b9-b2ad-19a6a8597b72)

✅ DynamoDB Record Created  

![DynamoDB screenshoot](https://github.com/user-attachments/assets/36d52ba6-ea3c-4962-8132-485fc51429ed)


✅ Project Status & Future Enhancements

Current Status:
✅ Fully functional – deployed successfully – tested and running

Potential Improvements:

Add a frontend web UI for uploads


NLP sentiment analysis via Amazon Comprehend

DLQ + retry logic for failed invocations

Support for TIFF, DOCX, and other file types

S3 lifecycle rules to save storage costs



---

📄 License

This project is licensed under the MIT License.


---

🙌 Credits

Built with ❤ by Gloria Ejike as a hands-on cloud engineering and serverless practice project.
🌐 Visit my blog → http://greentechguruonline.wordpress.com 
