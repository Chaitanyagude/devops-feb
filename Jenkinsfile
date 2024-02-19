pipeline{
    agent any
    
    stages {
        stage('Git Clone') {
            steps{
                git 'https://github.com/Chaitanyagude/devops-feb.git'     
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                  sh 'docker build -t chaitug/nodeapp:latest .'
                }
            }
        }
        stage('Docker Login') {
            steps {
                script {
                    sh 'docker login -u chaitug -p Chaitu@123'
                }   
            }
        }
        stage('Docker Push') {
            steps {
                script {
                    sh 'docker push chaitug/nodeapp:latest'
                }
            }    
        }
    }   
}
