===============================================================================
                            LEOPARD SKIN WEB APPLICATION
===============================================================================

OVERVIEW
--------
This repository contains a full-stack web application that creates an AI-powered 
"Digital Twin" - an intelligent chatbot that represents Jake Chuang and can 
interact with visitors on his personal website. The application combines modern 
web technologies with AWS cloud services to deliver a personalized AI experience.

PROJECT STRUCTURE
-----------------
twin/
├── frontend/                 # Next.js React application
│   ├── app/                 # App router pages and layouts
│   ├── components/          # React components (twin.tsx - main chat interface)
│   └── public/             # Static assets
├── backend/                 # FastAPI Python backend
│   ├── server.py           # Main API server
│   ├── lambda_handler.py   # AWS Lambda entry point
│   ├── context.py          # AI prompt engineering
│   ├── data/               # Personal data for the digital twin
│   │   ├── facts.json      # Personal facts about Jake
│   │   ├── summary.txt     # Professional summary
│   │   ├── linkedin.pdf    # LinkedIn profile data
│   │   └── style.txt       # Communication style guide
│   └── requirements.txt    # Python dependencies
├── terraform/              # Infrastructure as Code
│   ├── main.tf            # AWS resources (S3, Lambda, API Gateway, CloudFront)
│   ├── variables.tf       # Configuration variables
│   ├── terraform.tfvars   # Development environment settings
│   └── prod.tfvars        # Production environment settings
└── scripts/               # Deployment automation
    ├── deploy.sh/.ps1     # Deployment scripts
    └── destroy.sh/.ps1    # Cleanup scripts

TECHNOLOGY STACK
----------------
Frontend:
- Next.js 15.5.4 (React 19.1.0)
- TypeScript
- Tailwind CSS 4
- Lucide React (icons)

Backend:
- FastAPI (Python)
- AWS Bedrock (AI/LLM)
- AWS Lambda (serverless)
- AWS S3 (conversation memory)
- Pydantic (data validation)

Infrastructure:
- AWS (us-east-1 region)
- Terraform (Infrastructure as Code)
- S3 (static hosting + memory storage)
- CloudFront (CDN)
- API Gateway (HTTP API)
- Lambda (serverless compute)
- DynamoDB (state locking)

AI/ML:
- AWS Bedrock (Amazon Nova models)
- Custom prompt engineering
- Conversation memory persistence

KEY FEATURES
------------
1. AI-Powered Digital Twin
   - Represents Jake Chuang's personality and knowledge
   - Trained on personal data (LinkedIn, facts, communication style)
   - Maintains conversation context and memory

2. Modern Web Interface
   - Real-time chat interface
   - Responsive design
   - Professional UI with Tailwind CSS
   - Avatar support for personal branding

3. Cloud-Native Architecture
   - Serverless backend (AWS Lambda)
   - Scalable infrastructure
   - Global CDN delivery
   - Automated deployment

4. Conversation Memory
   - Persistent chat history in S3
   - Session-based conversations
   - Context-aware responses

5. Multi-Environment Support
   - Development and production configurations
   - Environment-specific variables
   - Automated deployment scripts

DEPLOYMENT
----------
The application is designed for AWS deployment with the following architecture:

1. Frontend: Static site hosted on S3 + CloudFront
2. Backend: Serverless API using Lambda + API Gateway
3. AI: AWS Bedrock for LLM inference
4. Storage: S3 for conversation memory
5. Infrastructure: Managed by Terraform

Quick Start:
1. Configure AWS credentials
2. Set up Terraform variables
3. Run deployment scripts
4. Access via CloudFront URL

DEVELOPMENT
-----------
Local Development:
- Frontend: npm run dev (port 3000)
- Backend: python server.py (port 8000)
- Requires AWS credentials for Bedrock access

Environment Variables:
- NEXT_PUBLIC_API_URL: Backend API endpoint
- AWS credentials for Bedrock and S3 access
- CORS_ORIGINS: Allowed frontend origins

PERSONALIZATION
---------------
The digital twin is personalized through several data files:
- facts.json: Personal information and preferences
- summary.txt: Professional background and expertise
- linkedin.pdf: LinkedIn profile data
- style.txt: Communication style and personality traits

These files are used to create a comprehensive AI prompt that makes the 
chatbot respond as Jake Chuang would, maintaining his voice and knowledge.

SECURITY & PRIVACY
------------------
- CORS properly configured for production domains
- S3 buckets with appropriate access controls
- Environment-based configuration management
- No sensitive data in version control

LICENSE
-------
See LICENSE.txt for license information.

AUTHOR
------
Jake Chuang - Product Leader & Entrepreneur
Building products to empower people and elevate human potential.

===============================================================================
