pipeline {
    agent any

    environment{
        dbUser = credentials("db_user")
    }

    stages {

        stage('Checkout'){
            steps{
                git url: 'https://github.com/tvivektripathi/Codex.git', branch: 'main'
                bat "dir"
            }
        }

        stage('Setup') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'db_user', usernameVariable:"myuser", passwordVariable: "password")]){

                    echo "The dbUser id :${dbUser}; db user: ${myuser} and password: ${password}"
                }
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
                

            }   
            steps {
                echo "Running Deployment"
                echo "The dbUser id :${dbUser}; db user: ${dbUser_usr} and password: ${dbUser_psw}"
            
            }
        } 
    }
}