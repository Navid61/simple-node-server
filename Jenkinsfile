pipeline {
    agent any

    stages {
        // Checkout stage to pull code from GitHub
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:Navid61/simple-node-server.git' 
            }
        }

        // Uncommented and fixed stage for installing dependencies using npm ci
        stage('Install Dependencies (npm ci)') {
            agent {
                docker {
                    image 'node:18-alpine' // Ensure the image name is correct and consistent with Docker Hub
                    label 'node-18-alpine' // Optional: add a label if using a specific agent
                }
            }
            steps {
                // Use shell commands to install dependencies
                sh 'npm ci'
            }
        }

        // Test stage to check if npm test is running correctly
        stage('Test Installation') {
            steps {
                script {
                    // Run tests or commands to check the installation
                    echo 'Running npm test (replace with your actual test command if needed)'
                    // Uncomment and replace the next line with your actual test command
                    // sh 'npm test'
                }
            }
        }
    }
}
