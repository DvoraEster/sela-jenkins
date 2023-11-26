pipeline {
    agent any

//    environment {
        // Define environment variables for Docker Hub credentials
 //       DOCKER_HUB_USERNAME = credentials('6b5cc6c1-f2fc-4333-b98f-7f12623065f4').username
//        DOCKER_HUB_PASSWORD = credentials('6b5cc6c1-f2fc-4333-b98f-7f12623065f4').password
//    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the Git repository
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build Docker image from the Dockerfile in the repository
                script {
                    docker.withRegistry('https://registry.hub.docker.com', '6b5cc6c1-f2fc-4333-b98f-7f12623065f4') {
                        def customImage = docker.build("dvoraester/hello-sela:1.0")
                    }
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                // Push the Docker image to Docker Hub
                script {
                    docker.withRegistry('https://registry.hub.docker.com', '6b5cc6c1-f2fc-4333-b98f-7f12623065f4') {
                        customImage.push()
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Build and push to Docker Hub successful!'
        }
        failure {
            echo 'Build or push to Docker Hub failed!'
        }
    }
}
