pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Compile') {
            agent {
                docker {
                    image 'gradle:6.6.1-jre14-openj9'
                    reuseNode true
                }
            }
            steps {
                sh 'cd calculator && ./gradlew compileJava'
            }
        }
        stage('Unit Tests') {
            agent {
                docker {
                    image 'gradle:6.6.1-jre14-openj9'
                    reuseNode true
                }
            }
            steps {
                sh 'cd calculator && ./gradlew test'
            }
        }
    }
}
