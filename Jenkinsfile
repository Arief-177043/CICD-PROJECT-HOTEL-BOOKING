pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Arief-177043/CICD-PROJECT-HOTEL-BOOKING.git'
            }
        }

        stage('Backend - Install & Run') {
            steps {
                dir('backend') {
                    sh 'npm install'
                    sh 'nohup npm start > backend.log 2>&1 &'
                }
            }
        }

        stage('Frontend - Install & Run') {
            steps {
                dir('frontend') {
                    sh 'npm install'
                    sh 'nohup npm start > frontend.log 2>&1 &'
                }
            }
        }
    }
}
