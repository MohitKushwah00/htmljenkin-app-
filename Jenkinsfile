pipeline {
  agent any


    stage('Build Docker Image') {
      steps {
        sh 'docker build -t hi-anime-app .'
      }
    }

    stage('Run Container') {
      steps {
        sh 'docker rm -f hi-anime-container || true'
        sh 'docker run -d --name hi-anime-container -p 8081:80 hi-anime-app'
      }
    }
  }

  post {
    success {
      echo "✅ Your anime site is live at http://localhost:8081"
    }
  }
}
