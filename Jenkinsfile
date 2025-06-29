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
        step([
            $class: 'Publisher',
            reportFilenamePattern: '**/target/surefire-reports/testng-results.xml',
            failureOnFailedTest: true,
            showFailedBuilds: true
        ])
    }
}


}
