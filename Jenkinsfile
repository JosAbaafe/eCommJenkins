pipeline{
    agent any
    stages{
        stage('Git Checkout'){
            steps{
                git credentialsId: '1f76b417-da94-45ee-812d-f68110bddad3', url: 'https://github.com/JosAbaafe/eCommJenkins.git'
            }
        }
        stage('Build'){
            steps{
               sh 'virtualenv venv && . venv/bin/activate && pip install -r requirements.txt && python tests.py'
            }
        }
        stage('Unit-Test'){
            steps{
                sh 'python app/manage.py test'
            }
        }
        stage('Deploy'){
            steps{
                echo 'echo ........'
            }
        }
    }
}