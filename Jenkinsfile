pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    def image = docker.build("todoapp:${env.BUILD_ID}")
                }
            }
        }

 

        stage('Deploy') {
            steps {
                script {
                    // Deploy the Docker container
                    def image = docker.image("todoapp:${env.BUILD_ID}")
                    image.inside {
                        sh 'docker run -d -p 9000:5000 todoapp:${env.BUILD_ID}'
                    }
                }
            }
        }
    }
}