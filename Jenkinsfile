pipeline {
    agent any
        {
            docker {
                image 'python:3.10-slim'
                args '-v /var/jenkins_home:/var/jenkins_home'
            }
        }

    stages {
        stage('Checkout code') {
            steps {
                git branch: 'main', credentialsId: 'Git-id', url: 'https://github.com/Srvvignesh92/learn_jenkins'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
    }
}