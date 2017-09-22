pipeline {
  agent any
  stages {
    stage('Preparation') {
      steps {
        git(url: 'https://github.com/nyanim/jenkins-docker.git', branch: 'master')
      }
    }
    stage('Build') {
      steps {
        sh 'docker build -t nyanim/jenkins .'
      }
    }
    stage('Push') {
      steps {
        sh '''docker login -u=$DOCKER_USERNAME -p=$DOCKER_PASSWORD
docker push nyanim/jenkins'''
      }
    }
  }
}