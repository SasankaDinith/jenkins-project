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
                echo "URL: ${env.JENKINS_URL}"
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Build ID: ${env.BUILD_ID}"
                echo "Build Tag: ${env.BUILD_TAG}"
            }
        }
    }

}
