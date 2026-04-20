pipeline {
    agent  any
    
    stages {
        stage('Checkout the code') {
            steps {
                git branch: 'main', credentialsId: 'Git-id', url: 'https://github.com/Srvvignesh92/learn_jenkins'
            }
        }

        stage('Install dependencies') {
            steps {
                sh '''
                    # Create a virtual environment and install dependencies.
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run tests') {
            steps {
                sh '''
                    # Activate the virtual environment and run tests...
                    . venv/bin/activate
                    pytest tests/
                '''
            }
        }
        

    }
}