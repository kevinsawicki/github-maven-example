pipeline {
  agent none
  stages {
    stage('Buzz Build') {
      parallel {
        stage('Build Java 7') {
          agent any
          steps {
            sh '''mvn clean install -f example/pom.xml

echo "I am a ${BUZZ_NAME}"'''
          }
        }

        stage('Build Java 8') {
          agent any
          steps {
            sh 'echo "I am a ${BUZZ_NAME}"'
            archiveArtifacts(artifacts: 'example/target/***', fingerprint: true)
          }
        }

      }
    }

    stage('Buzz Test') {
      parallel {
        stage('Testing A 7') {
          agent any
          steps {
            sh 'mvn test -f example/pom.xml'
            junit '**/surefire-reports/**/*.xml'
          }
        }

        stage('Testing B 7') {
          agent any
          steps {
            sh '''sleep 10
echo done.'''
          }
        }

        stage('Testing A 8 ') {
          agent any
          steps {
            sh 'mvn test -f example/pom.xml'
          }
        }

        stage('Testing B 8 ') {
          agent any
          steps {
            sh '''sleep 10
echo done.'''
          }
        }

      }
    }

  }
  environment {
    BUZZ_NAME = 'Java 8 Bee'
  }
}