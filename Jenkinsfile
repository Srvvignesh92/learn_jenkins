pipeline {
    agent  any
    
    stages {
        stage('Checkout the code') {
            steps {
                git branch: 'main', credentialsId: 'Git-id', url: 'https://github.com/Srvvignesh92/learn_jenkins'
            }
        }
        stage('Install Python') {
            steps {
                sh '''
                    # Check if python3 already installed, skip if yes
                    if ! command -v python3 &> /dev/null; then
                        apt-get update
                        apt-get install -y python3 python3-pip python3-venv
                    else
                        echo "Python already installed: $(python3 --version)"
                    fi
                '''
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