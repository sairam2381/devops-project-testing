pipeline {
    agent any

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

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}