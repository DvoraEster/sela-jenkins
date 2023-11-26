pipeline {
    agent any

    stages {
        stage('Build1') {
            steps {
                echo 'Build12 DVORA'
                sh 'ls'
                sh 'docker build -t dvoraester/hello-sela:1.0 .'
            }
        }
        stage('Test') {
            steps {
                echo 'Test!'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy'
            }
        }
    }
}
