pipeline {
    agent any
    environment {
        VENV = 'venv'
    }
    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'python3 -m venv $VENV'
                sh '. $VENV/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh '. $VENV/bin/activate && pytest'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Despliegue simulado a entorno staging'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finalizado'
        }
        success {
            echo 'Pipeline exitoso'
        }
        failure {
            echo 'Pipeline fallido'
        }
    }
}
