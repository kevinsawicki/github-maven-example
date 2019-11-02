pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        dir(path: 'example') {
          sh 'apt-get update && apt-get install -y maven'
        }

      }
    }
  }
}