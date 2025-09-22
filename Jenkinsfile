pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sairam2381/devops-project-testing.git'
            }
        }////
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm run test'
            }
        }
      
    }
    post {
        success { echo "Pipeline completed successfully!" }
        failure { echo "Pipeline failed. Check the logs!" }
    }
}