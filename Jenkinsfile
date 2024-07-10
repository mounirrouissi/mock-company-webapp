pipeline {
    agent any

    environment {
        JAVA_HOME = 'C:\Users\thinkpad t490\.jdks\corretto-1.8.0_412'
    }

    stages {
        stage('Build') {
            steps {
                bat 'set PATH=%JAVA_HOME%\\bin;%PATH% && gradlew.bat assemble'
            }
        }
        stage('Test') {
            steps {
                bat 'set PATH=%JAVA_HOME%\\bin;%PATH% && gradlew.bat test'
            }
        }
    }
}