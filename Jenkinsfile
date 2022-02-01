pipeline {
    agent any
    
    parameters {
        string(name: 'Version', defaultvalue: ' ', description: 'version to deploy on prod')
        choice(name: 'Version', choices: ['1.1.0', '2.0.0'], description: '')
    }
    
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('')
     }
    stages {
        stage('Build') {
            steps {
                  echo 'Building the application'
                  echo "Building version ${NEW_VERSION}"
            }
        }
         stage('Test') {
             when {
                 expression {
                    BRACH_NAME == 'dev' || BRANCH_NAME == 'master'
                 }
             }
            steps {
                  echo 'Testing the application..'
            }
        }
         stage('Deploy') {
            steps {
                  echo 'Deploying the application..'
            }
        }
        
    }
    post {
        always {
        }
        
        failure {
        }
    }
}
