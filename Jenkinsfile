pipeline {
  agent {
    label 'WorkerEc2Node'
  }
  stages {
    stage('Git Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build Docker Image') {
      parallel {
        stage('Build Docker Image') {
          steps {
            sh 'cd vote && sudo docker build . -t 889521077131.dkr.ecr.us-east-1.amazonaws.com/ciimagerepo:${BUILD_NUMBER}'
            sh 'sudo docker push 889521077131.dkr.ecr.us-east-1.amazonaws.com/ciimagerepo:${BUILD_NUMBER}'
          }
}
