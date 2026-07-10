pipeline {
    agent any

    environment {
        DB_HOST = '192.168.2.1'
        USERNAME = 'user1'
        PASSWORD = 'password123'
    }

 
    stages {

        stage ('setup') {
            steps {
            
                echo "The Database IP is : ${DB_HOST}"
            }
        }

        stage ('Test') {
            steps {
                sh "ls -ltr"
                echo "Commit: ${env.GIT_COMMIT}"
                echo "Commit: ${env.JENKINS_URL}"
                echo "Commit: ${env.BUILD_NUMBER}"
              
                echo "Commit: ${env.BUILD_TAG}"
            }
        }
    }

}
