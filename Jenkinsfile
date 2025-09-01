pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker build -t asif9720/e-commerce/cartservice:v1.0.0 ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker push asif9720/e-commerce/cartservice:v1.0.0"
                    }
                }
            }
        }
    }
}
