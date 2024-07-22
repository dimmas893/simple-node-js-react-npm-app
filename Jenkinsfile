pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], browser: github('https://github.com/dimmas893/simple-node-js-react-npm-app.git'), extensions: [], userRemoteConfigs: [[credentialsId: '470e68b0-034e-459b-baef-56d732f0e5e0', url: 'https://github.com/dimmas893/simple-node-js-react-npm-app.git']])
            }
        }
    }
}
