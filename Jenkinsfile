pipeline {
    agent any

    stages {

        stage('Checkout'){
            steps{
                git url: 'https://github.com/tvivektripathi/Codex.git', branch: 'main'
                dir
            }
        }

        stage('Setup') {
            steps {
                pip "install -r requirements.txt"
            
            }
        }
        stage('Test') {
            steps {
                sh "pytest"
                
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