pipeline {
    agent {
      dockerfile true
    }
    stages {
        stage('maven_3_jdk_13') {
            steps {
                sh 'mvn --version'
                sh 'java -version'
                sh 'mvn install'
            }
        }
        stage('maven_3_jdk_8_slim') {
            steps {
                sh 'mvn --version'
                sh 'java -version'
                sh 'mvn install'
            }
        }
    }
}
