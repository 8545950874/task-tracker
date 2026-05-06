pipeline {
    agent any

    environment {
        KUBECONFIG_PATH = 'C:\\Users\\Anurag Singh\\.kube\\config'
    }

    stages {
        stage('Docker Build') {
            steps {
                bat "cd app && docker build -t anuragsinghak95/task-tracker:latest ."
            }
        }

        stage('K8s Deploy') {
            steps {
                echo "Deploying to Minikube using config at ${env.KUBECONFIG_PATH}"
                
                bat "kubectl --kubeconfig=\"${env.KUBECONFIG_PATH}\" apply -f k8s/deployment.yaml --validate=false"
                bat "kubectl --kubeconfig=\"${env.KUBECONFIG_PATH}\" apply -f k8s/service.yaml --validate=false"
            }
        }
    }
}
