node {
    /* Requires the Docker Pipeline plugin to be installed */
    withDockerContainer('node:16-buster-slim'){
        stage('Build') {
                checkout scm
                sh 'npm install'
            }
        
        stage('Copas') {
                checkout scm
                sh 'cp pom.xml .. '
                echo 'succes copy file'
  
        }
        
        stage('Test') {
                checkout scm
                sh 'cp package.json .. '
                sh './jenkins/scripts/test.sh' 
  
        }
       
        stage('Deliver') { 
                checkout scm
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
        }
        
    }
}
