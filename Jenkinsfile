pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your Django project from your version control system
                checkout scm
            }
        }

        stage('Setup Virtual Environment') {
            steps {
                // Set up virtual environment
                sh 'python3 -m venv venv'
                sh 'source venv/bin/activate'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Lint') {
            steps {
                // Run linting tools if needed
                sh 'flake8 .'
            }
        }

        stage('Test') {
            steps {
                // Run Django tests
                sh 'python manage.py test'
            }
        }

        stage('Deploy') {
            steps {
                // You can add deployment steps here if needed
                // For example, deploying to a server
            }
        }
    }

    post {
        always {
            // Clean up virtual environment
            sh 'deactivate || true'
        }

        success {
            echo 'Build successful!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
