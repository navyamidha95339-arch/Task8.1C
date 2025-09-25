pipeline {
    agent any

    triggers {
        // Poll SCM every 5 minutes
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build - Compile and package the application code (Maven/Gradle).'
            }
        }

        stage('Unit & Integration Tests') {
            steps {
                echo 'Run unit (JUnit) and integration tests (TestNG).'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analyze code quality and standards (SonarQube).'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Scan for security vulnerabilities (OWASP Dependency-Check/Snyk).'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploy application to staging environment (AWS EC2, Ansible/Jenkins).'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Run tests in staging (Selenium/Postman).'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploy application to production (AWS EC2, Ansible/Terraform/Jenkins).'
            }
        }
    }

    post {
        success { echo 'Pipeline completed successfully!' }
        failure { echo 'Pipeline failed. Check logs.' }
    }
}
