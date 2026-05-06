pipeline {
    agent any // Yeh line batati hai ki kisi bhi available node par chalao

    stages {
        stage('Test') {
            steps {
                // Saari commands 'steps' ke andar honi chahiye
                bat 'echo Hello Anurag, checking pipeline...'
            }
        }
        
        stage('Build') {
            steps {
                // Aapki purani commands yahan aayengi
                bat "docker build -t anuragsinghak95/task-tracker:latest ./app"
            }
        }
    }
}
