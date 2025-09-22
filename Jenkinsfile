pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Arief-177043/CICD-PROJECT-HOTEL-BOOKING.git'
            }
        }

stage('Backend - Build & Run') {
    dir('backend') {
        bat 'mvnw clean install -DskipTests'
        bat 'mvnw spring-boot:run &'
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
