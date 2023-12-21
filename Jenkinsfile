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
            archiveArtifacts(artifacts: 'example/target/***', fingerprint: true)
            stash(name: 'Buzz Java 7', includes: 'target/**')
          }
        }

        stage('Build Java 8') {
          agent any
          steps {
            sh 'echo "I am a ${BUZZ_NAME}"'
            archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
            stash(name: 'Buzz Java 8', includes: 'target/**')
          }
        }

      }
    }

    stage('Buzz Test') {
      parallel {
        stage('Testing A 7') {
          agent any
          steps {
            unstash 'Buzz Java 7'
            sh 'mvn test -f example/pom.xml'
            junit '**/surefire-reports/**/*.xml'
          }
        }

        stage('Testing B 7') {
          agent any
          steps {
            unstash 'Buzz Java 8'
            sh '''sleep 10
echo done.'''
          }
        }

        stage('Testing A 8 ') {
          agent any
          steps {
            unstash 'Buzz Java 8'
            sh 'mvn test -f example/pom.xml'
          }
        }

        stage('Testing B 8 ') {
          agent any
          steps {
            unstash 'Buzz Java 8'
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