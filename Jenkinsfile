pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'docker build -t ecommerce-app .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker stop ecommerce-app || exit /b 0'
                bat 'docker rm ecommerce-app || exit /b 0'
                bat 'docker run -d --name ecommerce-app -p 8081:80 ecommerce-app'
            }
        }
    }
}
