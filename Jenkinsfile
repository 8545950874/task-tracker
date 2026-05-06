pipeline {
    agent any 

    stages {
        stage('Test') {
            steps {
    
                bat 'echo Hello Anurag, checking pipeline...'
            }
        }
        
        stage('Build') {
            steps {
                bat "docker build -t anuragsinghak95/task-tracker:latest ./app"
            }
        }
    }
}
