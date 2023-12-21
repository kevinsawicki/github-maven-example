pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh 'mvn clean install -f example/pom.xml'
        archiveArtifacts(artifacts: 'example/target/***', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        sh 'mvn test -f example/pom.xml'
        junit '**/surefire-reports/**/*.xml'
        junit 'target/**/TEST*.xml'
      }
    }

  }
}