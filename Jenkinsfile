pipeline {
    agent any
    
    environment {
        DB_HOST = '192.168.12.1'
        USERNAME = 'user1'
        PASSWORD = 'password123'

    }
     
    stages {
        stage('Setup') {
            steps {
               
                echo "The database IP is: ${DB_HOST}" 
            }
        }
        stage('Test') {
            steps {
               
                echo "The DB username: ${USERNAME} and the password is: ${PASSWORD}"
            }
        }
    }
}
