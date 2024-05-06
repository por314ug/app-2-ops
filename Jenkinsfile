pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'hello-world-app'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/por314ug/app-2.git', branch: 'main'
            }
        }
      
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(env.DOCKER_IMAGE)
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.run("${env.DOCKER_IMAGE}:latest")
                }
            }
        }
    }
}
