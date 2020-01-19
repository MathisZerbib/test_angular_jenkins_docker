pipeline {
  agent {
    docker {
      image 'node:lts-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Run') {
      steps {
        sh 'npm run test'
      }
    }

  }
  environment {
    HOME = '.'
    CHROME_BIN = 'google-chrome'
  }
}