pipeline {
    agent any
    stages {
        stage('Build Image') {
            steps {
                sh 'docker build -t my-devops-app .'
            }
        }
        stage('Deploy Container') {
            steps {
                sh 'docker rm -f my-running-site || true'
                sh 'docker run -d -p 80:80 --name my-running-site my-devops-app'
            }
        }
    }
}
