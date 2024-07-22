pipeline {
    agent any

    tools {
        nodejs 'node'
    }

    environment {
        GIT_CREDENTIALS_ID = 'c67d0741-e72c-44a4-85dd-52dd554d4244'
        DOCKER_IMAGE = 'simple-node-js-react-npm-app:latest'
        DOCKER_CONTAINER = 'simple-node-js-react-npm-app-container'
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
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                sh 'docker build -t ${DOCKER_IMAGE} .'
            }
        }
        stage('Run Docker Container') {
            steps {
                // Stop and remove any existing container
                script {
                    def containerExists = sh(script: "docker ps -a | grep ${DOCKER_CONTAINER}", returnStatus: true)
                    if (containerExists == 0) {
                        sh "docker stop ${DOCKER_CONTAINER} && docker rm ${DOCKER_CONTAINER}"
                    }
                }
                // Run new Docker container
                sh 'docker run -d --name ${DOCKER_CONTAINER} -p 3000:3000 ${DOCKER_IMAGE}'
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
