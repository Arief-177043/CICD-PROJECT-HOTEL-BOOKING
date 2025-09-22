pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Backend - Install & Run') {
            steps {
                dir('backend') {
                    sh 'npm install'
                    // Run backend on port 5000 (or whatever you set in package.json)
                    sh 'nohup npm start > backend.log 2>&1 &'
                }
            }
        }

        stage('Frontend - Install & Run') {
            steps {
                dir('frontend') {
                    sh 'npm install'
                    // Run frontend on port 3000 (or whatever you set in package.json)
                    sh 'nohup npm start > frontend.log 2>&1 &'
                }
            }
        }
    }

    post {
        success {
            echo "✅ Frontend (port 3000) and Backend (port 5000) are running!"
        }
        failure {
            echo "❌ Build failed — check console output."
        }
    }
}
