pipeline {
    agent any
    
        stage('Build Docker Image') {
            steps {
                // Build Docker image from the Dockerfile in the repository
                sh 'docker build -t dvoraester/hello-sela:1.0 .'
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                // Push the Docker image to Docker Hub
               sh 'docker push dvoraester/hello-sela:1.0'
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
