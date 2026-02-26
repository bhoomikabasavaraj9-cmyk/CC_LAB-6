pipeline {
    agent any

    stages {

        stage('Build Backend Image') {
            steps {
                echo 'Building backend Docker image'
                sh '''
                  cd CC_LAB-6
                  docker build -t backend-app backend
                '''
            }
        }

        stage('Deploy Backend') {
            steps {
                echo 'Deploying backend container'
                sh '''
                  docker rm -f backend-pipeline || true
                  docker run -d --name backend-pipeline backend-app
                '''
            }
        }
    }
}
