pipeline {
  agent {
    node {
      label 'docker-lidor'
    }

  }
  stages {
    stage('checkout Code') {
      steps {
        git(url: 'https://github.com/lidorg-dev/Flask-Example.git', branch: 'main', changelog: true, poll: true)
      }
    }

    stage('Build') {
      steps {
        sh "docker build . -t lidorlg/flask-demo-int:${env.BUILD_ID}"
      }
    }

  }
}
