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
        sh 'npm run server'
      }
    }

    stage('Run') {
      steps {
        sh 'npm start'
      }
    }

  }
  environment {
    HOME = '.'
    CHROME_BIN = 'google-chrome'
  }
}