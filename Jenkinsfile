pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Arief-177043/CICD-PROJECT-HOTEL-BOOKING.git'
            }
        }

        stage('Backend - Build & Run') {
            steps {
                dir('backend') {
                    bat 'mvnw clean install -DskipTests'
                    bat 'start /B mvnw spring-boot:run'
                }
            }
        }

        stage('Frontend - Install & Build') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                    bat 'npm run build'
                    bat 'start /B npm start'
                }
            }
        }
    }
}
