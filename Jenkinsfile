pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:Navid61/simple-node-server.git' 
            }
        }

        stage('Install Dependencies (npm ci)') {
            agent {
                docker {
                    image 'node-18-alpine'
                }
            }
            steps {
                sh 'npm ci'
            }
        }

        stage('Test Installation') {
            steps {
                script {
                    // Add commands to test the installation here
                    // For example, you could run npm test or other tests specific to your project
                    echo 'Running npm test (replace with your actual test command if needed)'
                }
            }
        }
    }
}