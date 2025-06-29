pipeline {
    agent any

    tools {
        maven 'Maven_3.9.10' // Your configured Maven version
    }

    stages {
        stage('Build & Test') {
            steps {
                bat 'mvn clean test'
            }
        }
    }

    post {
        always {
            // This will now look for TestNG reports
            publishTestNGResults testNGPattern: '**/target/surefire-reports/testng-results.xml'
        }
    }
}
