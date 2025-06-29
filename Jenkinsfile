pipeline {
    agent any

    stages {
        stage('Build & Test') {
            steps {
                // Run Maven test (use 'bat' instead of 'sh' if you're on Windows)
                bat 'mvn clean test'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
