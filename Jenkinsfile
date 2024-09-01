pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the application. (Use Maven for building)'
                    sh 'echo "Build log" > build.log'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests. (Use JUnit or another test framework)'
                    sh 'echo "Unit and Integration Tests log" > test.log'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code quality...(Use Github & SonarQube for code analysis)'
                    sh 'echo "Code Analysis log" > code_analysis.log'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing security scan. (Use OWASP ZAP for security scanning)'
                    sh 'echo "Security Scan log" > security_scan.log'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to staging server. (Deploy to AWS EC2)'
                    sh 'echo "Deploy to Staging log" > deploy_staging.log'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging. (Integration tests on staging server)'
                    sh 'echo "Integration Tests on Staging log" > integration_staging.log'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to production server. (Deploy to AWS EC2)'
                    sh 'echo "Deploy to Production log" > deploy_production.log'
                }
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '*.log', allowEmptyArchive: true
            emailext to: 'hogang.matt@gmail.com',
                     subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                     body: """Pipeline ${currentBuild.fullDisplayName} finished with status: ${currentBuild.currentResult}.
                              Check the attached log for details.""",
                     attachmentsPattern: '*.log'
        }
    }
}
