Pipeline Script: 
pipeline {
  agent any
  tools {nodejs "node"}
  stages {
    stage('Build') {
      steps {
        git 'https://github.com/dimmas893/simple-node-js-react-npm-app.git'
        bat 'npm install'
      }}}}