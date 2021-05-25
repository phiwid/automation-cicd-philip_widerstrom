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
                    echo 'Frontend tests'
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