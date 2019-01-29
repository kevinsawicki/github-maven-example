pipeline {
    agent none
    stages {
        stage('maven_3_jdk_13') {
            agent {
                docker { 
                    image 'maven:3-jdk-13'
                    label 'slave-1'
                }
            }
            steps {
                sh 'mvn --version'
                sh 'java -version'
                sh 'mvn install'
            }
        }
        stage('maven_3_jdk_8_slim') {
            agent {
                docker { 
                    image 'maven:3-jdk-8-slim'
                    label 'slave-1'
                }
            }
            steps {
                sh 'mvn --version'
                sh 'java -version'
                sh 'mvn install'
            }
        }
    }
}
