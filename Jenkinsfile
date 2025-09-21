// pipeline {
//     agent {
//         docker { image 'node:18' }
//     }

//     stages {
//         stage('Checkout') {
//             steps {
//                 git 'https://github.com/sairam2381/devops-project-testing.git'
//             }
//         }

//         stage('Install Dependencies') {
//             steps {
//                 sh 'npm install'
//             }
//         }

//         stage('Run Tests') {
//             steps {
//                 sh 'npm test'
//             }
//         }

//         stage('Build') {
//             steps {
//                 sh 'npm run build'
//             }
//         }
//     }
// }

pipeline {
    agent any

    environment {
        // Optional: set Node environment if needed
        NODE_ENV = 'production'
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Pulling code from GitHub..."
                git branch: 'master', url: 'https://github.com/sairam2381/devops-project-testing.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing Node.js dependencies..."
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running unit tests..."
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                echo "Building the application..."
                sh 'npm run build'
            }
        }

        stage('Deployment') {
            steps {
                echo "Starting application..."
                // Adjust this command to your start script or process manager (pm2, forever, etc.)
                sh 'npm start &'
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully!"
        }
        failure {
            echo "Pipeline failed. Check the logs!"
        }
    }
}