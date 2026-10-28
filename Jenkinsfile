
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
                bat '"C:\\Users\\MISBAH\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t ecommerce-app .'
            }
        }

        stage('Deploy') {
            steps {
                bat '"C:\\Users\\MISBAH\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" stop ecommerce-app || exit /b 0'
                bat '"C:\\Users\\MISBAH\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" rm ecommerce-app || exit /b 0'
                bat '"C:\\Users\\MISBAH\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" run -d --name ecommerce-app -p 8081:80 ecommerce-app'
            }
        }
    }
}
