pipeline {
    agent any
    stages{
        
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t chaitug/python-image .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) {
                   sh 'docker login -u chaitug -p ${dockerhubpwd}'

}
                   sh 'docker push chaitug/python-image'
                }
            }
        }

    }
}
