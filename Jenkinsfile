pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    doGenerateSubmoduleConfigurations: false, 
                    extensions: [[$class: 'CloneOption', timeout: 60]], // Menambahkan timeout 60 detik
                    userRemoteConfigs: [[credentialsId: '470e68b0-034e-459b-baef-56d732f0e5e0', url: 'https://github.com/dimmas893/simple-node-js-react-npm-app.git']]
                ])
            }
        }
    }
}
