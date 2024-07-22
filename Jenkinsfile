pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '470e68b0-034e-459b-baef-56d732f0e5e0', url: 'https://github.com/jenkins-docs/simple-node-js-react-npm-app.git']])
            }
        }
    }
}
