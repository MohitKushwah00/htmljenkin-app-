pipeline {
  agent any

  stages {
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t htmljenkins-app .'
      }
    }

    stage('Run Container') {
      steps {
        sh 'docker rm -f htmljenkins-container || true'
        sh 'docker run -d -p 8081:80 --name htmljenkins-container htmljenkins-app'
      }
    }
  }
}
