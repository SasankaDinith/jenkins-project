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
                sh "pip install -r requirments.txt"
                echo "The Database IP is : ${DB_HOST}"
            }
        }

        stage ('Test') {
            steps {
                sh "pytest"
                echo "The database username: ${USERNAME} and the password is: ${PASSWORD}"
            }
        }

}
