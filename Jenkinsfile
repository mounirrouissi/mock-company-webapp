pipeline {
    agent any

    environment {
        JAVA_HOME = 'C:/Users/thinkpad t490/.jdks/corretto-1.8.0_412'
        GRADLE_OPTS = '-Dorg.gradle.daemon=false -Dorg.gradle.jvmargs="-Xmx2048m -XX:+HeapDumpOnOutOfMemoryError"'
    }

    options {
        timeout(time: 1, unit: 'HOURS')
    }

    stages {
        stage('Build') {
            steps {
                timeout(time: 15, unit: 'MINUTES') {
                    bat '''
                        set PATH=%JAVA_HOME%\\bin;%PATH%
                        gradlew.bat --no-daemon --stacktrace assemble
                    '''
                }
            }
        }
        stage('Test') {
            steps {
                timeout(time: 15, unit: 'MINUTES') {
                    bat '''
                        set PATH=%JAVA_HOME%\\bin;%PATH%
                        gradlew.bat --no-daemon --stacktrace test
                    '''
                }
            }
        }
    }
}