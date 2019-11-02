pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        dir(path: 'example') {
          sh 'mvn clean'
        }

      }
    }
  }
}