pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/chaitanyagude/my-data/Nodejs.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('chaitug/nodejs')
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        docker.image('chaitanyagude/nodejs').push('latest')
                    }
                }
            }
        }
    }
}
