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
               bat '''
                python --version
                python -m venv venv
                venv\\Scripts\\activate
                pip install -r requirements.txt
                '''            }
        }

        stage('Run Tests') {
            steps {
                bat '''
                venv\\Scripts\\activate
                pytest -v
                '''
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
