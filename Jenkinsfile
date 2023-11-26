pipeline {
    agent any

    stages {
        stage('Hello1') {
            steps {
               sh 'docker build -t dvoraester/hello-sela:${BUILD_NUMBER} .'
            }
        }
        stage('Hello2') {
            steps {
                sh 'docker push dvoraester/hello-sela:${BUILD_NUMBER}'
            }
        }
        stage('Hello3') {
            steps {
                echo 'Hello World3'
            }
        }
    }
}
