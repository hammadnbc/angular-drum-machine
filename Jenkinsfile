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
                sh 'npm install'
                sh 'npm run build'
                sh 'npm test'
                stash name: 'dist', includes: 'dist/'

            }
        }
    }
    
}
