pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh '''mvn clean install -f example/pom.xml

echo "I am a ${BUZZ_NAME}"'''
        archiveArtifacts(artifacts: 'example/target/***', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        sh 'mvn test -f example/pom.xml'
        junit '**/surefire-reports/**/*.xml'
      }
    }

  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}