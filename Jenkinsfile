pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-web-app .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker rm -f my-running-app || true'
                sh 'docker run -d -p 80:80 --name my-running-app my-web-app'
            }
        }
    }
}
