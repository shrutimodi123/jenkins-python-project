pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                 git branch: 'main',
                     url: 'https://github.com/shrutimodi123/jenkins-python-project.git'
            }
        }
        
        stage('Setup Environment') {
            steps {
                sh 'python -m venv venv'
                sh 'venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'venv/bin/pytest -v'
            }
        }
    }
    post {
        success {
            echo 'Build Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
    }
}
