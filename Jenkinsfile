pipeline {
  agent {
    docker {
      image 'node:lts-alpine3.11'
      args '-p 3000:3000'
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