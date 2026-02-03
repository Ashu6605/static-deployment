pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps { git 'https://github.com/Ashu6605/static-deployment.git' }
        }
        stage('Build Image') {
            steps { 
                sh 'docker build -t static-site .'
            }
        }
        stage('Run Container') {
            steps {
                sh '''
                docker stop static-site || true
                docker rm static-site || true
                docker run -d --name static-site -p 80:80 static-site
                '''
            }
        }
    }
}
