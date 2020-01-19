pipeline {
  agent {
    docker {
      image 'node:lts-alpine3.11'
      args '-p 8000:8000'
    }

  }
  stages {
    stage('error') {
      steps {
        sh 'npm install'
      }
    }

  }
}