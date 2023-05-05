pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout code') {
      steps {
        echo 'will checkout code'
      }
    }

    stage('Build') {
      steps {
        echo 'now we will build'
      }
    }

    stage('Test') {
      steps {
        echo 'now we will test'
      }
    }

    stage('Push to DockerHub') {
      steps {
        echo 'final step push to docker hub '
      }
    }

  }
}