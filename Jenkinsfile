pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Maven would be utilized here"
            }

            
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "JUnit would be utilized here"
            }
        }
        stage('Code Analysis') {
            steps {
                echo "SonarQube would be utilized here"
            }
        }
        stage('Security Scan') {
            steps {
                echo "OWASP ZAP would be used here"
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "AWS EC2 would be used here"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests on the staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "AWS EC2 would be used here"
            }
        }
        stage('Complete') {
            steps {
                echo "Completed"
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
