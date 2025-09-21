pipeline {
    agent {
        docker { image 'node:18' }  // official Node.js Docker image
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sairam2381/devops-project-testing.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }

    post {
        success { echo "Pipeline completed successfully!" }
        failure { echo "Pipeline failed. Check the logs!" }
    }
}