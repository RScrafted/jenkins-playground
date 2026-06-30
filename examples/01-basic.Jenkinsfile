pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'Repository checked out successfully.'
            }
        }

        stage('Inspect Workspace') {
            steps {
                echo "Workspace: ${env.WORKSPACE}"
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Environment') {
            steps {
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Branch: ${env.BRANCH_NAME ?: 'N/A'}"
            }
        }

        stage('Success') {
            steps {
                echo 'Basic pipeline completed successfully!'
            }
        }
    }

    post {
        always {
            echo 'Pipeline has finished.'
        }

        success {
            echo 'Build completed successfully.'
        }

        failure {
            echo 'Build failed.'
        }
    }
}