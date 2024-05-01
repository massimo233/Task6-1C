pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building with Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running tests with JUnit and Mockito'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan with OWASP ZAP'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 (staging)'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging server'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 (production)'
            }
        }
    }
    post {
        always {
	    emailext (
            	 to: 'salomonem4488@gmail.com',
                 subject: "Jenkins Pipeline Status",
                 body: "The pipeline has completed. Please check the logs.",
                 attachLog: true
	    )
        }
    }
}
