pipeline {
    agent any
    
    stages {
        stage('Docker Build') {
            steps {
               bat "cd app && docker build -t anuragsinghak95/task-tracker:latest ."
            }
        }
        stage('K8s Deploy') {
            steps {
                def kubeConfig = 'C:\\Users\\Anurag Singh\\.kube\\config'
                echo "Deploying to Minikube..."
                bat "kubectl --kubeconfig=\"${kubeConfig}\" apply -f k8s/deployment.yaml --validate=false"
                bat "kubectl --kubeconfig=\"${kubeConfig}\" apply -f k8s/service.yaml --validate=false"
            }
        }
    }
}
