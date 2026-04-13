pipeline {
    agent  {
        docker {
            image 'python:3.9-slim'
         } }
    
    stages {
        stage('Checkout the code') {
            steps {
                git branch: 'main', credentialsId: 'Git-id', url: 'https://github.com/Srvvignesh92/learn_jenkins'
            }
        }
        stage('Install dependencies') {
            steps {
                sh '''
                    # 1. Ensure venv exists
                    python3 -m venv venv
                    
                    # 2. Use the pip inside the venv to install
                    ./venv/bin/pip install --upgrade pip
                    ./venv/bin/pip install -r requirements.txt
                '''
            }
        }
    }
}