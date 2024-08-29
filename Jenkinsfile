pipeline {
    agent any
    
    stages {
        }
        stage('Christopher Ho Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("chrisho7/python-app")
                }
            }
        }
        stage('Christopher Ho - Login to Dockerhub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-credentials') {
                        echo 'Logged in to DockerHub'
                    }
                }
            }
        }
        stage('Christopher Ho - Push image to Dockerhub') {
            steps {
                script {
                    dockerImage.push('latest')
                }
            }
        }
    }
}
