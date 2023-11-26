pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
               sh 'docker build -t dvoraester/hello-sela:${BUILD_NUMBER} .'
            }
        }
        stage('docker push') {
            steps {
                sh 'docker push dvoraester/hello-sela:${BUILD_NUMBER}'
            }
        }
        stage('End') {
            steps {
                echo 'Hello End'
            }
        }
    }
}
