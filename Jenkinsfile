
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kalpitpatel-267/student-flask-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t student-flask-app .'
            }
        }

        stage('Deploy Application') {
            steps {
                bat 'docker rm -f student-app || exit /b 0'
                bat 'docker run -d -p 5000:5000 --name student-app student-flask-app'
            }
        }
    }
}

