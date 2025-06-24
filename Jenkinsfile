pipeline {
    agent any

    environment{
        DB_HOST="192.168.12.1"
        dbUser=credentials('db_user')
        PASSWORD="password123"
    }

    stages {

        // stage('Checkout'){
        //     steps{
        //         git url: 'https://github.com/tvivektripathi/Codex.git', branch: 'main'
        //         bat "dir"
        //     }
        // }

        stage('build') {
            steps {
                bat "mvn clean install"
                // echo "The database ip is :${DB_HOST}"

                echo "Commit: ${env.GIT_COMMIT}"
                echo "secret: ${dbUser}"
                echo "user: ${dbUser_user}"
                echo "password: ${dbUser_psw}"
            
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
                echo "The database user :${USERNAME} and password: {$PASSWORD}"
            }
            steps {
                echo "Running Deployment"
                
            }
        } 
    }
}