pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the application.'
                    // Example command that generates a log file
                    bat 'echo Build started > build.log'
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests.'
                    // Example command that generates a log file
                    bat 'echo Tests started > test.log'
                }
            }
        }

        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code quality.'
                    // Example command that generates a log file
                    bat 'echo Code analysis started > code-analysis.log'
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing security scan.'
                    // Example command that generates a log file
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
                    // Example command that generates a log file
                    bat 'echo Integration tests started > integration-tests.log'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to production server.'
                    // Example command that generates a log file
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
                                <p>Build Status: ${currentBuild.currentResult}</p>
                                <p>Build Number: ${currentBuild.number}</p>
                                <p><a href="${env.BUILD_URL}">Console Logs</a></p>
                            </body>
                        </html>''',
                from: 'hogang.matt@gmail.com',
                mimeType: 'text/html',
                attachmentsPattern: '**/*.log' // Adjust the pattern to match your log files
            )
        }
    }
} //emailext attachLog: true, body: 'The security scan has: failed', to:'hogang.matt@gmail.com', subject: 'Pipeline build status: Security'
