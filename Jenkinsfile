pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh 'clean install -f example/pom.xml'
      }
    }

    stage('Buzz Test') {
      steps {
        sh 'test -f example/pom.xml'
      }
    }

  }
}