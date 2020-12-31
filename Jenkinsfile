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
                def namespace="qa"
                def ENV="my-python-app"

                withCredentials([file(credentialsId: ...)]) {
                    // change context with related namespace
                    sh "kubectl config set-context $(kubectl config current-context) --namespace=${namespace}"

                    //Deploy with Helm
                    echo "Deploying"
                    sh "helm upgrade --install road-dashboard -f values.${ENV}.yaml --set tag=$TAG --namespace ${namespace}"  
                    //sh 'kubectl apply -f my-python-app.yaml --namespace qa'
                }
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
