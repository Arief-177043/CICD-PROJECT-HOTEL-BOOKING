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
                    bat 'npm install'
                    bat 'start /B npm start > backend.log 2>&1'
                }
            }
        }

        stage('Frontend - Install & Run') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                    bat 'start /B npm start > frontend.log 2>&1'
                }
            }
        }
    }
}
