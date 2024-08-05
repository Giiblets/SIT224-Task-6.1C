pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the application. (Use Maven for building)'

                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests. (Use JUnit or another test framework)'
                }
            }
        }

        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code quality...(Use Github & SonarQube for code analysis)'
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing security scan. (Use OWASP ZAP for security scanning)'
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to staging server. (Deploy to AWS EC2)'
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging. (Integration tests on staging server)'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to production server. (Deploy to AWS EC2)'
                }
            }
        }
    }

    post {
        success{
            mail to: "hogang.matt@gtmail.com",
            subject: "Build Status Email",
            body: "Build was successful!"
        }
    }
}
