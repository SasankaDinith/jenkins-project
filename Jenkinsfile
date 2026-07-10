pipeline {
    agent any

    environment {
        IMAGE_NAME = "sanjeevkt720/jenkins-flask-app"
        IMAGE_TAG = "${IMAGE_NAME}:${BUILD_NUMBER}"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kodekloudhub/jenkins-project.git'

                sh 'ls -ltr'
            }
        }

        stage('Setup') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'pytest'
                sh 'whoami'
            }
        }

        stage('Login to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'dockerhubpwd', variable: 'DOCKER_PASSWORD')]) {
                    sh 'echo $DOCKER_PASSWORD | docker login -u sanjeevkt720 --password-stdin'
                }
                echo 'Docker Hub login successful'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ${IMAGE_TAG} .'
                sh 'docker images'
                echo 'Docker image built successfully'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push ${IMAGE_TAG}'
                echo 'Docker image pushed successfully'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
