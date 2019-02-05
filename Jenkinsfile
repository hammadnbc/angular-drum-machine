pipeline {
    
    agent any
    
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:6-alpine'
		    args '-p 3000:3000 -p 5000:5000'
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
