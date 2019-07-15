pipeline {
  agent {
    node {
      label 'vm01'
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
    stage('Run tests') {
      steps {
        dir(path: 'flask-app') {
          sh '''docker-compose down;
docker-compose build flask-app;
docker-compose run flask-app pytest -v --junit-xml=/var/opt/junit-report/report.xml;
docker-compose down'''
        }

      }
    }
    stage('Archive JUnit-formatted test results') {
      steps {
        junit 'flask-app/junit-report/report.xml'
        dir(path: 'flask-app/junit-report') {
          deleteDir()
        }

      }
    }
  }
}