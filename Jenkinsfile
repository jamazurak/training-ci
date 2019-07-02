pipeline {
  agent any
  stages {
    stage('Echo some text') {
      steps {
        sh 'echo "Hello!"'
      }
    }
    stage('Run app') {
      steps {
        dir(path: 'flask-app') {
          sh 'docker-compose up -d --build'
        }

      }
    }
  }
}