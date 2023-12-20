pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh 'mvn clean install -f example/pom.xml'
      }
    }

    stage('Buzz Test') {
      steps {
        sh 'mvn test -f example/pom.xml'
      }
    }

  }
}