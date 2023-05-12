pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/lidorg-dev/Flask-Example.git', branch: 'main', changelog: true, poll: true)
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t flask-example:$BUILD_ID .'
      }
    }

    stage('Test') {
      steps {
        sh '''docker run -d -p 6969:6969 --name flask-demo flask-example:$BUILD_ID



'''
        sh 'sleep 5'
        sh 'curl localhost:6969'
        sh 'docker stop flask-demo && docker rm flask-demo'
      }
    }

    stage('Push to DockerHub') {
      steps {
        echo 'final step push to docker hub '
      }
    }

  }
}