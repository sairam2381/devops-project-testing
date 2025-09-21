pipeline {
    agent any

    tools {
        nodejs "node16"   // name you configured in Jenkins
    }

    stages {
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
        always {
            junit 'reports/junit/*.xml'
        }
    }
}
