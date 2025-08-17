pipeline {
    agent any

    tools {
        maven 'Maven 3.8.6' // Make sure this matches your Jenkins Maven tool name
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/dubemifedi/simple-maven-app.git'
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

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
