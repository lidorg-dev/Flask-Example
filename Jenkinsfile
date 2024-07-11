pipeline {
  agent {
    node {
      label 'docker-lidor'
    }

  }
  stages {
    stage('checkout Code') {
      steps {
        checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-ssh', url: 'git@github.com:lidorg-dev/Flask-Example.git']])
      }
    }

    stage('Build') {
      steps {
        sh "docker build . -t lidorlg/flask-demo-int:${env.BUILD_ID}"
      }
    }

    stage('Push') {
      withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {

      steps {
        sh "docker login -u $USERNAME -p $PASSWORD"
        sh "docker push lidorlg/flask-demo-int:${env.BUILD_ID}"
      }
      }
    }

  }
}
