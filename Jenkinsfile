pipeline {
  agent {
    node {
      label 'centos-7-slave'
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
        sh 'docker build -t flask-example:latest .'
      }
    }

    stage('Test') {
      steps {
        sh 'echo "hello"'
      }
    }

    stage('Package') {
      steps {
        sh 'echo "hello"'
      }
    }

  }
}
