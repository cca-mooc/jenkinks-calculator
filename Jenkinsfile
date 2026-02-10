pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Compile') {
            steps {
                sh 'cd calculator && ./gradlew compileJava'
            }
        }
        stage('Unit Tests') {
            steps {
                sh 'cd calculator && ./gradlew test'
            }
        }
    }
}
