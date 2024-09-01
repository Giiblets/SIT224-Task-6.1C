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
            post {
                always {
                    archiveArtifacts artifacts: '**/target/*.log', allowEmptyArchive: true
                    mail to: 'hogang.matt@gmail.com',
                         subject: "Unit and Integration Tests: ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                         body: """Stage: Unit and Integration Tests
                                  Status: ${currentBuild.currentResult}
                                  Check the attached log for details.""",
                         attachLog: true
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
            post {
                always {
                    archiveArtifacts artifacts: '**/dependency-check-report.html', allowEmptyArchive: true
                    mail to: 'hogang.matt@gmail.com',
                         subject: "Security Scan: ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                         body: """Stage: Security Scan
                                  Status: ${currentBuild.currentResult}
                                  Check the attached log for details.""",
                         attachLog: true
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
        always {
            archiveArtifacts artifacts: '**/target/*.log', allowEmptyArchive: true
            mail to: 'hogang.matt@gmail.com',
                 subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                 body: """Pipeline ${currentBuild.fullDisplayName} finished with status: ${currentBuild.currentResult}.
                          Check the attached log for details.""",
                 attachLog: true
        }
    }
}
