pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim' 
            args '-p 3030:3030' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
