pipeline {
    agent any
    environment{
        DOCKER_TAG = getDockerTag()
    }
    stages {
        stage('deploy staging') {
            steps {
                // builing application
                echo "deploy staging...." 
                sh "kubectl apply -f my-python-app.yaml"
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