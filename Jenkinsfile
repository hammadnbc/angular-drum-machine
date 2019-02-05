pipeline {
    
    agent any
    
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:10'
			args '-u root:root'
		    args '-p 3000:3000 -p 5000:5000'
                }			    
            }
		environment {
			CI = 'true'
		}	
            steps {
                sh 'npm install'
                sh 'npm run build'
                sh 'npm test'
                stash name: 'dist', includes: 'dist/'
            }
        }
    }
    
}
