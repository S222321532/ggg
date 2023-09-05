pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package' // Assuming Maven is installed and configured
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                sh 'mvn test' // Assuming Maven is installed and configured
            }
        }
        stage('Code Analysis') {
            steps {
                withSonarQubeEnv('SonarQube Server') {
                    sh 'mvn sonar:sonar' // Assuming SonarQube plugin is configured
                }
            }
        }
        stage('Security Scan') {
            steps {
                sh 'mvn org.owasp:dependency-check-maven:check' // OWASP Dependency-Check plugin
            }
        }
        stage('Deploy to Staging') {
            steps {
                sh 'aws s3 cp target/my-app.war s3://your-staging-bucket/' // AWS CLI for S3 deployment
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // You can run Selenium or other integration tests here
            }
        }
        stage('Deploy to Production') {
            steps {
                sh 'aws s3 cp target/my-app.war s3://your-production-bucket/' // AWS CLI for S3 deployment
            }
        }
    }
    
    post {
        success {
            // Send a success notification email with logs as attachment
            emailext subject: 'Pipeline Success',
                body: 'The Jenkins pipeline has completed successfully.',
                attachmentsPattern: '**/*'
        }
        failure {
            // Send a failure notification email with logs as attachment
            emailext subject: 'Pipeline Failure',
                body: 'The Jenkins pipeline has failed.',
                attachmentsPattern: '**/*'
        }
    }
}
