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

✅ S3 Upload Trigger  
![S3 Upload Trigger](screenshot/S3 real world project.png)


✅ Lambda Triggered (CloudWatch Logs)  
![CloudWatch Logs](screenshot/cloudwatch 1.png)

✅ DynamoDB Record Created  
![DynamoDB Record Created](screenshot/DynamoDB  screenshoot.png)


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
