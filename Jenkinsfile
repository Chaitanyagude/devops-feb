pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/chaitanyagude/devops-feb.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('my-docker-image')
                }
            }
        }
        stage('Push Docker Image to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        docker.image('my-docker-image').push('latest')
                    }
                }
            }
        }
    }
}
