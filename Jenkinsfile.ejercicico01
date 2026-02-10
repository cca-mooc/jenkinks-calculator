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
                    image 'eclipse-temurin:11-jdk'
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
                    image 'eclipse-temurin:11-jdk'
                    reuseNode true
                }
            }
            steps {
                sh 'cd calculator && ./gradlew test'
            }
        }
    }
}
