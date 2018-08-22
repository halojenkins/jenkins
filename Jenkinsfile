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
            sh 'docker tag ps halojenkins/test'
            sh 'docker push halojenkins/test'
        }
    }
  }
}