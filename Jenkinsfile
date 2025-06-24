pipeline {
    agent any

    environment{
        DB_HOST="192.168.12.1"
        USERNAME="user1"
        PASSWORD="password123"
    }

    stages {

        // stage('Checkout'){
        //     steps{
        //         git url: 'https://github.com/tvivektripathi/Codex.git', branch: 'main'
        //         bat "dir"
        //     }
        // }

        stage('Setup') {
            steps {
                bat "pip install -r requirements.txt"
                // echo "The database ip is :${DB_HOST}"
            
            }
        }
        // stage('Test') {
        //     steps {
        //         bat "pytest"
                
        //     }
        // }    
        stage('Deployment') {
            input {
                message "Do you want to proceed further?"
                ok "Yes"
                echo "The database user :${USERNAME} and password: "$PASSWORD"
            }
            steps {
                echo "Running Deployment"
                
            }
        } 
    }
}