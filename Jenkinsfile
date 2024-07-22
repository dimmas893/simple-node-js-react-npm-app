pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    doGenerateSubmoduleConfigurations: false, 
                    extensions: [[$class: 'CloneOption', timeout: 30]], // Menambahkan timeout 30 detik
                    userRemoteConfigs: [[credentialsId: '470e68b0-034e-459b-baef-56d732f0e5e0', url: 'https://github.com/jenkins-docs/simple-node-js-react-npm-app.git']]
                ])
            }
        }
    }
}
