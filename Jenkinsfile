pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the application.'
                    bat 'echo Build started > build.log'
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests.'
                    bat 'echo Tests started > test.log'
                }
            }
        }

        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code quality.'
                    bat 'echo Code analysis started > code-analysis.log'
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing security scan.'
                    bat 'echo Security scan started > security-scan.log'
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to staging server.'
                    // Example command that generates a log file
                    bat 'echo Deployment started > deploy-staging.log'
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging.'
                    bat 'echo Integration tests started > integration-tests.log'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to production server.'
                    bat 'echo Deployment to production started > deploy-production.log'
                }
            }
        }
    }

    post {
        always {
            emailext(
                to: 'hogang.matt@gmail.com',
                subject: "Pipeline Status: ${currentBuild.currentResult}",
                body: '''<html>
                            <body>
                                <p>Please see the attached Logs for more detail</p>
                            </body>
                        </html>''',
                from: 'hogang.matt@gmail.com',
                mimeType: 'text/html',
                attachmentsPattern: '**/*.log' 
            )
        }
    }
} 
