pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/naveengadde123/my-flask-app'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t simple-flask-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker-compose down || true
                docker-compose up -d
                '''
            }
        }
    }
}
