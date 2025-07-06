---

# 🧾 Serverless OCR Document Processor with AWS

This project provides a *fully serverless Optical Character Recognition (OCR)* pipeline built entirely with AWS services and deployed using *CloudFormation. It automates the extraction of text from documents uploaded to an S3 bucket using **Amazon Textract, stores the extracted content in **DynamoDB, and delivers a summary of the results via email using **Amazon SES—all orchestrated through **AWS Lambda*.

This solution is ideal for anyone looking to build document automation workflows, enhance AI-driven processes, or explore practical serverless architectures on AWS.

---

## ✨ *Features*

- *Automated OCR:* Automatically extracts text from uploaded PDF, PNG, and JPG documents.  
- *Scalable & Serverless:* Leverages AWS Lambda and S3 for a highly scalable, pay-as-you-go architecture.  
- *Persistent Storage:* Stores all extracted text in Amazon DynamoDB for easy retrieval and querying.  
- *Email Notifications:* Sends an email summary of the extracted text via Amazon SES.  
- *Infrastructure as Code:* Deploys the entire solution using a single CloudFormation template, ensuring repeatable and consistent deployments.  
- *Real-time Monitoring:* Integrates with CloudWatch for comprehensive logging and monitoring of the entire pipeline.

---

## 🚀 *Tech Stack*

- *Amazon S3:* Stores uploaded documents (PDF, PNG, JPG) and acts as the trigger source.  
- *AWS Lambda:* Executes the core OCR processing logic, triggered by S3 upload events.  
- *Amazon Textract:* The powerful OCR service that performs intelligent text extraction from documents.  
- *Amazon DynamoDB:* A NoSQL database used to persist the extracted textual content under a unique documentId.  
- *Amazon SES:* Sends extracted text summaries and notifications to a verified email address.  
- *AWS CloudFormation:* Defines and deploys all necessary AWS resources as a single, cohesive stack.  
- *AWS CloudWatch:* Provides logging and monitoring for all service interactions within the pipeline.

---

## 📂 *Project Structure*

. ├── template.yaml           # CloudFormation template defining the entire AWS stack └── README.md               # Project documentation and guide (this file)

---

## ⚙ *How It Works*

- *Document Upload:* A user uploads a supported document (.pdf, .png, or .jpg) to the designated S3 input bucket.  
- *Lambda Trigger:* The S3 upload event automatically triggers an AWS Lambda function.  
- *Textract Processing:* The Lambda function invokes Amazon Textract to perform asynchronous text extraction on the uploaded document.  
- *Data Storage:* Once Textract completes the extraction, the Lambda function stores the extracted text content in an Amazon DynamoDB table, indexed by a unique documentId.  
- *Email Notification:* Simultaneously, a summary of the extracted text (or the full text, depending on configuration) is sent via email using Amazon SES to a pre-configured recipient.  
- *Logging:* AWS CloudWatch captures detailed logs of every step of the execution lifecycle, aiding in debugging and monitoring.

---

## 🔐 *Prerequisites*

Before deploying this project, ensure you have the following:

- An AWS Account  
- AWS CLI configured with appropriate credentials  
- Your AWS account must be in *Amazon SES sandbox mode, and you need at least one **verified email address* in SES. This email will be used as both the sender and recipient for notifications.  
- Sufficient IAM permissions to deploy CloudFormation stacks and create/manage S3 buckets, Lambda functions, Textract, DynamoDB, and SES resources.

---

## 📦 *Deploy This Project*

Follow these steps to deploy the serverless OCR processor to your AWS account:

### 1. Clone the repository:
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

2. Review and customize template.yaml (optional):

You might want to adjust resource names, S3 bucket names, or other parameters within the template.yaml file to suit your preferences.

3. Deploy via AWS CLI:

Replace you@example.com with your verified SES email address.

aws cloudformation deploy \
  --template-file template.yaml \
  --stack-name Serverless-OCR-Processor \
  --capabilities CAPABILITY_NAMED_IAM \
  --parameter-overrides SenderEmail=you@example.com RecipientEmail=you@example.com

--template-file template.yaml: Specifies the CloudFormation template to deploy

--stack-name Serverless-OCR-Processor: Sets a name for your CloudFormation stack

--capabilities CAPABILITY_NAMED_IAM: Acknowledges that the template creates IAM roles

--parameter-overrides: Passes the required email addresses to the stack


4. Wait for Deployment:

Deployment may take a few minutes. Monitor its progress in the CloudFormation console.

5. Test the Pipeline:

Locate the input S3 bucket created by the stack (found in CloudFormation Outputs or S3 console).
Upload a test .pdf, .png, or .jpg file to this bucket.

6. Check Your Inbox:

Watch your inbox for an email containing the extracted text results! ✉


---

📸 Screenshot

✅ S3 Bucket Upload



✅ Lambda Triggered Successfully



✅ CloudWatch Logs




✅ DynamoDB Record Created




---

✅ Project Status & Future Enhancements

This project is currently:

✅ Fully functional and deployed: Provides a robust serverless OCR solution

💡 Great for: Document automation, AI workflows, serverless demos, and personal learning


🔮 Potential Future Enhancements:

Frontend UI: Simple web interface for document uploads

Support for More Formats: Add support for TIFF, DOCX, etc.

Advanced Text Processing: Integrate Amazon Comprehend for NLP

Error Handling & DLQs: Improve resilience for failed jobs

Cost Optimization: Use lifecycle rules in S3

OCR Job Status Tracking: Handle long Textract jobs more elegantly



---

📄 License

This project is licensed under the MIT License.
See the LICENSE file in the root of the repository for full details.


---

🙌 Credits

Built with ❤ by Gloria Ejike as a hands-on cloud engineering and serverless practice project.

🌐 Visit My Blog: GreenTech Guru Online
