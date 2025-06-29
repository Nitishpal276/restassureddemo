pipeline {
    agent any

    tools {
        maven 'Maven_3.9.10'  // same name as Jenkins Maven config
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
        publishTestNGResults testNGPattern: '**/target/surefire-reports/testng-results.xml'
    }
}

}
