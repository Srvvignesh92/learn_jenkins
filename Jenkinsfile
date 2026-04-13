pipeline {
    agent any

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