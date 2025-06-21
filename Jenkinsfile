pipeline {
    agent any

    stages {

        stage('Checkout'){
            steps{
                git url: 'https://github.com/tvivektripathi/Codex.git', branch: 'main'
                bat "dir"
            }
        }

        stage('Setup') {
            steps {
                bat "pip install -r requirements.txt"
            
            }
        }
        stage('Test') {
            steps {
                bat "pytest"
                
            }
        }    
        stage('Deployment') {
            input {
                message "Do you want to proceed further?"
                ok "Yes"
            }
            steps {
                echo "Running Deployment"
                
            }
        } 

            
    }
}