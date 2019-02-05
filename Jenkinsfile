pipeline {
    
    agent any
    
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:10'
		    args '-p 3000:3000 -p 5000:5000'
                }
    environment {
        CI = 'true'
    }			    
            }
	
            steps {
                sh 'sudo -u node npm install'
                sh 'sudo -u node npm run build'
                sh 'sudo -u node npm test'
                stash name: 'dist', includes: 'dist/'
            }
        }
    }
    
}
