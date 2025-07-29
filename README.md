# Secure_deployment_on_ebcli
provides a detailed deployment of a mini retalishop e-commerce application into aws eb
## Step-by-Step Plan (Elastic Beanstalk)
### 1. Prerequisites

AWS Account (with admin or deployment permissions).

Installed Tools:

        AWS CLI → pip install awscli

        EB CLI → pip install awsebcli or pipx install awsebcli

        Git

Your e-commerce application code (Flask/Django, Node.js, Laravel, etc.).

Bandit and Safety for security analysis

Jenkins

SonarQube


### ARCHITECTURAL DESIGN

<img width="1536" height="1024" alt="architecture design" src="https://github.com/user-attachments/assets/0af5ffdf-ca15-47fe-b30e-26bc55a31b2f" />

### Jenkins Setup

Install Jenkins (on an EC2 instance or local machine)

Install required plugins:

        GitHub

        Pipeline

        SonarQube Scanner

        AWS Elastic Beanstalk Deployment Plugin (or AWS CLI)

Configure Jenkins with:

        AWS Credentials (IAM user/role)

        SonarQube Server URL and Token
next step
