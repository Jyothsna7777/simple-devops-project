pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t simple-website .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                sudo docker rm -f website || true
                sudo docker run -d --name website -p 80:80 simple-website
                '''
            }
        }
    }
}

