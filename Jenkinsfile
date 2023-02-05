node {
    /* Requires the Docker Pipeline plugin to be installed */
    withDockerContainer('node:16-buster-slim').inside {
        stage('Build') {
                sh 'npm install'
            }
        
        stage('Test') { 
                sh 'docker images'
                sh './jenkins/scripts/test.sh' 
  
        }
       
        stage('Deliver') { 
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
        }
        
    }
}
