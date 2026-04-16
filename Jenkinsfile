pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/srinivassindhanur7-dotcom/bookstore-app1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t your-dockerhub-username/bookstore-app1 .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push your-dockerhub-username/bookstore-app1'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 80:8080 your-dockerhub-username/bookstore-app1'
            }
        }
    }
}
