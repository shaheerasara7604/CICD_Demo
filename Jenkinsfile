pipeline {
    agent any
    tools {
        maven 'Maven 3.9.11'   // Updated Maven version
        jdk 'JDK 21'           // Keep this as exact name from Jenkins config
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }
    post {
        failure {
            echo 'Build or tests failed.'
        }
        success {
            echo 'Build and tests succeeded.'
        }
    }
}
