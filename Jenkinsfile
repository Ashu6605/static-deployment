pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t static-site .'
            }pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t static-site .'
            }
        }

        stage('Deploy Container') {
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
