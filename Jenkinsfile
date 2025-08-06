pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build -t flask-jenkins-app .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh 'echo "No tests defined yet"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Container...'
                sh '''
                    docker stop flask-app || true
                    docker rm flask-app || true
                    docker run -d -p 5000:5000 --name flask-app flask-jenkins-app
                '''
            }
        }
    }
}
