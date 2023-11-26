pipeline {
    agent any

    stages {
        stage('Hello1') {
            steps {
               sh 'docker build -t dvoraester/hello-sela:1.1 .'
            }
        }
        stage('Hello2') {
            steps {
                sh 'docker push dvoraester/hello-sela:1.1'
            }
        }
        stage('Hello3') {
            steps {
                echo 'Hello World3'
            }
        }
    }
}
