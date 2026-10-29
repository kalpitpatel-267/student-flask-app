
pipeline {
    agent any

    environment {
        DOCKER = 'C:\\Users\\Kalpit\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kalpitpatel-267/student-flask-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat '"%DOCKER%" version'
                bat '"%DOCKER%" build -t student-flask-app .'
            }
        }

        stage('Deploy Application') {
            steps {
                bat '"%DOCKER%" rm -f student-app'
                bat '"%DOCKER%" run -d -p 5000:5000 --name student-app student-flask-app'
            }
        }
    }
}


