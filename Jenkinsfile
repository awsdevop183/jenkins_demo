pipeline {
    agent any

    stages {
        stage('Create Docker image') {
            steps {
                sh 'docker build -t demo:v1 .'
            }
        }
        stage('Deleting old container') {
            steps {
                sh 'docker rm -f demo'
            }
        }
        
        
        stage('Create a container') {
            steps {
                sh 'docker run -d --name demo -p 84:80 demo:v1'
            }
        }
        stage('Dangling Image remove') {
            steps {
                sh 'docker image prune -f'
            }
        }
        
    }
}
