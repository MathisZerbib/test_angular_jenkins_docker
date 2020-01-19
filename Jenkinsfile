pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm run test'
      }
    }

  }
  environment {
    HOME = '.'
    CHROME_BIN = 'chromium-browser'
  }
}