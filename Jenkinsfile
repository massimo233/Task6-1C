pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building with make'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running tests with Parasoft C/C++ unit testing'
            }
            post {
                always {
                    emailext (
                        to: 'salomonem4488@gmail.com',
                        subject: "Jenkins Pipeline Test Status: ${currentBuild.currentResult}",
                        body: "Unit and Integration Test Status: ${currentBuild.currentResult}",
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan with CodeSonar'
            }
            post {
                always {
                    emailext (
                        to: 'salomonem4488@gmail.com',
                        subject: "Jenkins Pipeline Security Scan Status: ${currentBuild.currentResult}",
                        body: "Security Scan Status: ${currentBuild.currentResult}",
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging server'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production'
            }
        }
    }
}
