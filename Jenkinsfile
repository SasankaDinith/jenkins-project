pipeline {
    agent any
    
    environment {
         SERVER_CREDS = credentials('server-creds')

    }
     
    stages {
        stage('Setup') {
            steps {
                echo "My creds: ${SERVER_CREDS}"
                echo "My creds: ${SERVER_CREDS_USR}"
                echo "My creds: ${SERVER_CREDS_PSW}"
            }
        }
        stage('Test') {
            steps {
                sh "pytest"                
            }
        }
    }
}
