pipeline {
    agent any
    environment{
        DOCKER_TAG = "v2"
    }
    stages {
        stage('Build docker image') {
            steps {
                // builing application
                echo "building...." 
            }
        }
        stage('Push on Dockerhub'){
            steps{
                echo "pushing...." 
            }
        }
        stage('Test code'){
            steps {
                // testing application before updateing in cluster
                echo "Testing code" 
            }
        }
        stage('Deploy QA'){
            steps{
                // oh yeah go execute and update application
                echo "Deployment QA" 
                sh 'kubectl apply -f my-python-app.yaml --namespace qa'
            }
        }
        stage('Test check'){
            steps{
                // oh yeah go execute and update application
                echo "Test healthchecks" 
            }
        }
        stage('Deploy Production'){
            steps{
                // oh yeah go execute and update application
                echo "Deployment Production" 
            }
        }
    }
}
