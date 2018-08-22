pipeline {
  agent any
  stages {
    stage('myStage'){
      steps {
        sh 'ls -la'
        sh 'whoami'
      }
    }
    stage('Dockerization') {
        steps {
            sh 'sudo docker login -u halojenkins -p adg12TR45uuq'
            sh 'docker rmi ps:latest --force'
            sh 'docker build ./ -t ps'
            sh 'docker tag ps haloplatform/dex-pl-website:1.0.0'
            sh 'docker push haloplatform/dex-pl-website:1.0.0'
        }
    }
  }
}