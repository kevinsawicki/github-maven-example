pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        dir(path: 'example') {
          sh 'sudo apt-get update && apt-get install -y maven'
        }

        sh 'mvn clean'
      }
    }
  }
}