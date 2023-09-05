pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Use a build automation tool like Maven to compile and package your code"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Use test automation tools for unit and integration tests (e.g., JUnit, TestNG)"
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Use a code analysis tool (e.g., SonarQube) to analyze your code"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Use a security scanning tool (e.g., OWASP ZAP) to identify vulnerabilities"
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploy the application to a staging server (e.g., AWS EC2)"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests on the staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy the application to a production server (e.g., AWS EC2)"
            }
        }
    }
    
    post {
        success {
            mail to: "samiabdullah2004@gmail.com",
            subject: "Build Status Email",
            body: "Build was successful!"
        }
        failure {
            mail to: "samiabdullah2004@gmail.com",
            subject: "Build Status Email",
            body: "Build failed"
        }
    }
}
