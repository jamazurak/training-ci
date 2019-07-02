pipeline {
  agent any
  stages {
    stage('Echo some text') {
      steps {
        sh 'echo "Hello!"'
      }
    }
    stage('') {
      steps {
        dir(path: 'flask-app') {
          sh 'docker-compose up -d --build'
        }

      }
    }
  }
}