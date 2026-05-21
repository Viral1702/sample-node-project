pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git url: 'https://github.com/Viral1702/sample-node-project.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sample-node-app:latest .'
            }
        }

        stage('Deploy / Run Container') {
            steps {
                sh '''
                docker compose down
                docker compose up -d
                '''
            }
        }
    }
}