pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    credentialsId: 'SHA256:7QQIMkzw59n640kYcKk2vtghCFEEFmlxizx456AQdtM',
                    url: 'git@github.com:Rishabhdev-ui/jenkins-CICD.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t django-cicd .'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'docker run django-cicd python manage.py test'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 8000:8000 --name django-app django-cicd'
            }
        }
    }
}
