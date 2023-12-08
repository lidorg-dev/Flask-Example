pipeline {
  agent {
    node {
      label 'centos-7-slave'
    }

  }
  stages {
    stage('cehckokut code') {
      steps {
        git(url: 'https://github.com/lidorg-dev/Flask-Example.git', branch: 'main', changelog: true, poll: true)
      }
    }

  }
}