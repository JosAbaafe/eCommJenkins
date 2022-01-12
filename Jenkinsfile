pipeline{
    agent any
    stages{
        stage('Git Checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '1f76b417-da94-45ee-812d-f68110bddad3', url: 'https://github.com/JosAbaafe/eCommJenkins.git']]])
            }
        }
        stage('Build'){
            agent {
                docker {
                    image 'python:3-alpine'
                }
            }
            steps{
                bat 'pip install -r requirement.txt'
            }
        }
        stage('Unit-Test'){
            steps{
                bat 'python app/manage.py test'
            }
        }
        stage('Deploy'){
            steps{
                bat 'python manage.py runserver'
            }
        }
    }
}