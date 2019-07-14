pipeline {
  agent {
    node {
      label 'instance-1'
    }

  }
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