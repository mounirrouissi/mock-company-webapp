pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'gradlew.bat assemble'
            }
        }
        stage('Test') {
            steps {
                bat 'gradlew.bat test'
            }
        }
    }
}