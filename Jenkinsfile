pipeline {
    agent any
     stages {
        stage('Build') {
            steps {
                echo 'Building code using Maven'
            }
        }
        stage('Unit & Integration Tests') {
            steps {
                echo 'Running unit tests with JUnit and Mockito'
                echo 'Running integration tests with Postman and Newman'
            }
             post {
          success {
            mail to: "minhtien2049@gmail.com",
            subject: "Unit & Integration Tests",
            body: "Success"
          }
        }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube '
                
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for vulnerabilities with SAST tool OWASP ZAP'
                
            }
            post {
          success {
            mail to: "minhtien2049@gmail.com",
            subject: "Security Scan",
            body: "Success"
          }
        }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging server AWS EC2 or ECS'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
            }
            post {
          success {
            mail to: "minhtien2049@gmail.com",
            subject: "Integration Tests on Staging",
            body: "Success"
          }
        }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production server AWS EC2 or ECS'
            }
        }
    }
}