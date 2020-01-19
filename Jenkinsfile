pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:lts-alpine'
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
        sh '''RUN curl -sL https://deb.nodesource.com/setup_8.x | bash - \\
    && apt-get update \\
    && apt-get install -y nodejs
# Install Google Chrome
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \\
    && sh -c \'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list\' \\
    && apt-get update && apt-get install -y google-chrome-stable'''
      }
    }

  }
  environment {
    HOME = '.'
  }
}