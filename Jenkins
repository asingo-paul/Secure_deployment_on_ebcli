pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'     // change to your AWS region
        EB_APP_NAME = 'flask-ecommerce'      // Elastic Beanstalk app name
        EB_ENV_NAME = 'flask-ecommerce-env'  // Elastic Beanstalk environment
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/asingo-paul/Secure_deployment_on_ebcli.git'
            }
        }
        stage('Install Tools') {
            steps {
                sh '''
                pip install --quiet --upgrade pip
                pip install bandit safety awsebcli --quiet
                '''
            }
        }
        stage('Security Scan - Bandit') {
            steps {
                sh 'bandit -r . || true'
            }
        }
        stage('Dependency Security Check - Safety') {
            steps {
                sh 'safety check -r requirements.txt --full-report || true'
            }
        }
        stage('Deploy to AWS Elastic Beanstalk') {
            steps {
                sh '''
                eb init ${EB_APP_NAME} --region ${AWS_DEFAULT_REGION} --platform "Python 3.11"
                eb deploy ${EB_ENV_NAME}
                '''
            }
        }
    }
}
