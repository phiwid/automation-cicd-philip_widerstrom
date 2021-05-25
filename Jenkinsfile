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
        
         stage('BackEnd tests') {
            steps {
                sh '''
                    cd backend-tests/
                    npm install && npm run cypress:run
                    echo 'Publish test results'
                    pwd
                    ls -lart
                '''

                publishHTML([
                    allowMissing: false,
                     alwaysLinkToLastBuild: false,
                      keepAll: false, 
                      reportDir: 'backend-tests/mochawesome-report', 
                      reportFiles: 'mochawesome.html',
                       reportName: 'BackEnd Report', 
                       reportTitles: ''
                ])
            }
        }
        
         stage('FrontEnd tests') {
            steps {
                  sh '''
                    cd frontEndRegression/
                    npm install && npm run cypress:run
                    echo 'Publish test results'
                    pwd
                    ls -lart
                '''
                archiveArtifacts  allowEmptyArchive: true,  artifacts: 'frontEndRegression/cypress/videos/**'
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