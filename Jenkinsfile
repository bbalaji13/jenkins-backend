pipeline {
    agent any  // Run this pipeline on any available agent
    
    stages {
        stage('Build Backend') {
            steps {
                // Set up a Python virtual environment and install backend dependencies
                sh 'python3 -m venv venv'  // Create a virtual environment
                sh '. venv/bin/activate && pip install -r requirements.txt'  // Activate venv and install dependencies
            }
        }

        stage('Deploy Backend') {
            steps {
                // Restart the backend application using PM2 and Python 3 interpreter
                sh 'pip install flask'  // Ensure Flask is installed
                sh 'pm2 restart app.py --interpreter=python3'  // Restart the backend using PM2  
            }
        }
    }
}
