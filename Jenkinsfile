pipeline {

    agent any 

    stages {
        stage('Checkout') {
            steps {
              checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ClaudiuMarian98/ToDoApp']])
            }
        }


        stage('Docker Image') {
            steps {
          sh 'docker build -t todoapp1 .'
            }
        }
    }
}