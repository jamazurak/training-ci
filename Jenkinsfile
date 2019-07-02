pipeline {
  agent any
  stages {
    stage('Echo some text') {
      steps {
        sh 'echo "Hello!"'
      }
    }
    stage('error') {
      steps {
        git(url: 'https://github.com/jamazurak/training-ci', branch: 'jenkins', credentialsId: '5a:72:b3:ef:59:a6:62:4b:e8:8a:f6:07:c3:d2:ba:82')
      }
    }
  }
}