pipeline {
    agent any
    stages {
        stage('Deploy/Build app') {
            steps {
                sh '''
                    echo 'Application deployed successfully'
                '''
            }
        }
        
         stage('Frontend tests') {
            steps {
                sh '''
                    cd backend-tests/
                    npm install && npm run cypress:run
                    echo 'Publish test result'
                    pwd
                    ls -lart
                '''
            }
        }
        
         stage('Backend tests') {
            steps {
                sh 'pwd'
                sh 'ls -lart'
            }
        }
        
             stage('Performance test') {
            steps {
                sh 'pwd'
                sh 'ls -lart'
            }
        }
    }
}