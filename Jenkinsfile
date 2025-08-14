pipeline {
    agent any
    tools {
        maven 'Maven 3.9.11'
        jdk 'JDK 21'
    }
    environment {
        JAVA_HOME = "${tool 'JDK 21'}"
        PATH = "${env.JAVA_HOME}\\bin;${env.PATH}"
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
