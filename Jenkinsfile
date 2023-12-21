pipeline {
  agent none
  stages {
    stage('Buzz Build') {
      agent {
        node {
          label 'jdk7-node'
        }

      }
      steps {
        sh '''mvn clean install -f example/pom.xml

echo "I am a ${BUZZ_NAME}"'''
        archiveArtifacts(artifacts: 'example/target/***', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      parallel {
        stage('Testing A') {
          agent {
            node {
              label 'jdk7-node'
            }

          }
          steps {
            sh 'mvn test -f example/pom.xml'
            junit '**/surefire-reports/**/*.xml'
          }
        }

        stage('Testing B') {
          agent {
            node {
              label 'jdk7-node'
            }

          }
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