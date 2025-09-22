# 💬 Kimberly - Serverless Banking Chatbot

A serverless **banking chatbot** built with **Amazon Lex V2**, **AWS Lambda (Python 3.12)**, **AWS CloudFront** and **AWS CloudFormation**, enabling users to:  
- Check balances across multiple account types (Checking, Savings, Credit (Credit card, American Express, Visa, Mastercard, Amex), Recurring Deposit).  
- Transfer funds securely between accounts.  
- Handle multi-turn conversations with context awareness and validation.

This project demonstrates how to integrate **NLU (Natural Language Understanding)** with **serverless compute** and **infrastructure-as-code (IaC)** for scalable, production-ready conversational applications.

Video Link of Demonstration: https://drive.google.com/file/d/1_gMfklVozPQqy872O-zEKwIhBvWeF8TU/view?usp=sharing

---

## 🚀 Features
- **5 Intents**: `WelcomeIntent`, `CheckBalance`, `FollowupCheckBalance`, `TransferFunds`, `FallbackIntent`.  
- **Context-Aware Dialogs**: Maintains session with TTL of **90s / 5 turns**.  
- **Slot Validation**: Custom `accountType` slot with **4 whitelisted values** (Checking, Savings, Credit, Recurring Deposit).  
- **Transfer Safety**: Requires elicitation (`maxRetries=2`) and confirmation prompts before fund transfers.  
- **Serverless Deployment**: Lambda backend + CloudFront distribution for low-latency access.  
- **Source-Controlled**: Code tracked via Git & GitHub for reproducibility.

---

## 🛠️ Tech Stack & Tools
- **Amazon Lex V2** – intents, slots, contexts, fallback handling  
- **AWS Lambda (Python 3.12)** – backend fulfillment (`lambda_function.py`)  
- **AWS CloudFormation / SAM** – Infrastructure as Code for Lex bot, Lambda, aliases, permissions  
- **AWS CloudFront** – Deployment & CDN  
- **Python Standard Library** – `json`, `decimal`, `random`  
- **Git + GitHub** – version control & collaboration  
- **Notion** – documentation  

---

## 📂 Project Structure
├── lambda_function.py # Lambda backend handler

├── template.yaml # AWS SAM / CloudFormation template

├── README.md # Project documentation

└── docs/ # Design & flow documentation


---

## ⚙️ Setup & Deployment

### 1. Clone Repository
git clone (https://github.com/aprajita0401/Kimberly-A-Banking-Bot-Using-Amazon-Lex/)

cd kimberly-banking-chatbot

### 2. Build and Deploy Infrastructure
Use AWS SAM to build and deploy all resources:
sam build
sam deploy --guided


This process will provision the following AWS resources:  
- Lex Bot (Kimberly)  
- Lambda Function (LexBotFunction)  
- CloudFront Distribution  
- Necessary IAM permissions  

### 3. Update Lex Intents (Optional)
If you make changes to Lex intents in `template.yaml`, deploy updates by:
sam deploy


### 4. Test Chatbot
Use the Amazon Lex test console or integrate the bot via the CloudFront distribution URL for web access.

---

## 📊 Metrics & Highlights
- 5 Intents implemented including error fallback handling.  
- Context TTL: 90 seconds / 5 turns for multi-turn conversations.  
- Lambda Config: 128 MB memory, 3-second timeout, Python 3.12 runtime.  
- Custom Slot: Account type slot supports 4 values with elicitation retries and confirmation prompts.  

---

## 🖼️ Architecture

       User
         |
   [Amazon Lex V2]
        
         |
   
   +-----v-----+
  
   | AWS Lambda |  <-- Python 3.12 runtime (lambda_function.py)
  
   +-----+-----+
        
         |
   
   [AWS CloudFront]
        
         |
      
   (Frontend/UI)


---
## Refer PDF (Kimberly_A_Banking_ChatBot_Using_Amazon_Lex.pdf)
- I have documented every step while creating this project. One can follow the PDF, if they are interested in having hands-on experience with Amazon Lex.

## 🤝 Contributing

- Fork the repo  
- Create a feature branch (`feature/new-intent`)  
- Commit changes and push  
- Open a Pull Request  

---

## ✨ Acknowledgements

- Amazon Lex Developer Guide  
- AWS Lambda Documentation  
- AWS SAM Documentation










