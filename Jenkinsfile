pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the application...'
                    //sh 'echo "Build log: Application built successfully." > build.log'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running Unit and Integration Tests...'
                    //sh 'echo "Unit and Integration Tests log: All tests passed." > test.log'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Performing Code Analysis...'
                    //sh 'echo "Code Analysis log: No issues found." > code_analysis.log'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing Security Scan...'
                   // sh 'echo "Security Scan log: No vulnerabilities detected." > security_scan.log'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to Staging...'
                   // sh 'echo "Deploy to Staging log: Deployed successfully." > deploy_staging.log'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running Integration Tests on Staging...'
                    //sh 'echo "Integration Tests on Staging log: All tests passed." > integration_staging.log'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to Production...'
                    //sh 'echo "Deploy to Production log: Deployed successfully." > deploy_production.log'
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
