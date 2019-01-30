pipeline {
    agent none
    stages {
        stage('maven_3_jdk_13') {
            agent {
              dockerfile {
                filename 'Dockerfile.jdk13'
              }
            }
            steps {
                sh 'mvn --version'
                sh 'java -version'
            }
        }
        stage('maven_3_jdk_8_slim') {
            agent {
              dockerfile {
                filename 'Dockerfile.jdk8'
              }
            }
            steps {
                sh 'mvn --version'
                sh 'java -version'
            }
        }
    }
}
