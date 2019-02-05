pipeline {
    
    agent any
    
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:10'
			args '-u root:root'
                }			    
            }	
            steps {
		    sh 'apt-get update'
		    sh 'apt-get install -y sudo'
                sh 'sudo -u node npm install'
		sh 'sudo -u node npm run build'
                sh 'sudo -u node npm test'
                stash name: 'dist', includes: 'dist/'

            }
        }
    }
    
}
