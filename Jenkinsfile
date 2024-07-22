pipeline {
    agent any

    tools {
        nodejs 'node'
    }

    environment {
        GIT_CREDENTIALS_ID = 'c67d0741-e72c-44a4-85dd-52dd554d4244'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git branch: 'main', url: 'https://github.com/dimmas893/simple-node-js-react-npm-app.git', credentialsId: "${GIT_CREDENTIALS_ID}"
            }
        }
        stage('Verify Node.js and npm') {
            steps {
                // Verify Node.js installation
                sh 'node -v'
                // Verify npm installation
                sh 'npm -v'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install project dependencies
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                // Build the React project
                sh 'npm run build'
            }
        }
        stage('Archive') {
            steps {
                // Archive the build output
                archiveArtifacts artifacts: 'build/**', allowEmptyArchive: true
            }
        }
    }
}
