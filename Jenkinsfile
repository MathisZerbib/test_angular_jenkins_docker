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

    stage('Server') {
      parallel {
        stage('Server') {
          steps {
            sh 'npm run server'
          }
        }

        stage('App') {
          steps {
            sh 'npm start'
          }
        }

        stage('Test') {
          steps {
            sh 'npm run test'
          }
        }

      }
    }

  }
  environment {
    HOME = '.'
    CHROME_BIN = 'google-chrome'
  }
}