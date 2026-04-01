pipeline {
    agent {
        docker {
            image 'maven:3.9.14-eclipse-temurin-21-alpine'
        }
    }

    stages {

        stage('Checkout') {
            steps {
                // scarica il codice dal repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Build completata con successo!'
        }
        failure {
            echo 'Build fallita!'
        }
    }
}