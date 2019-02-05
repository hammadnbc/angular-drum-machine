pipeline {
    
    agent any
    
    stages {
        stage('Build') {
	
            steps {
                sh 'sudo -u node npm install'
                sh 'sudo -u node npm run build'
                sh 'sudo -u node npm test'
                stash name: 'dist', includes: 'dist/'

            }
        }
    }
    
}
