pipeline {
    agent any
    
    stages {
        stage('Docker Build') {
            steps {
                bat "docker build -t anuragsinghak95/task-tracker:latest ./app"
            }
        }
        stage('K8s Deploy') {
            steps {
                bat "kubectl apply -f k8s/deployment.yaml"
                bat "kubectl apply -f k8s/service.yaml"
            }
        }
    }
}
