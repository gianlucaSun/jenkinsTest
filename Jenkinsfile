pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
        
        stage('Deploy local') {
    		steps {
        		bat 'copy target\\*.jar C:\\tmp\\appoggio\\'
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