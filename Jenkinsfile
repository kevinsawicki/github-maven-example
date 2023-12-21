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
      parallel {
        stage('Testing A') {
          steps {
            sh 'mvn test -f example/pom.xml'
            junit '**/surefire-reports/**/*.xml'
          }
        }

        stage('Testing B') {
          steps {
            sh '''sleep 10
echo done.'''
          }
        }

      }
    }

  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}