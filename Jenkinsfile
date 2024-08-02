pipeline {
    agent any
    
    environment {
        DEPLOY_SERVER = '65.0.142.195'
        SSH_CREDENTIALS_ID = 'your-ssh-credentials-id'  // Replace with your actual credentials ID
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/anujkem/memory-game.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'echo "Building the project..."'
                // Add any actual build steps here if needed
            }
        }
        
        stage('Deploy') {
            steps {
                sshagent([env.SSH_CREDENTIALS_ID]) {
                    sh """
                    ssh -o StrictHostKeyChecking=no ubuntu@${env.DEPLOY_SERVER} << EOF
                    cd /var/www/html
                    sudo rm -rf memory-game
                    git clone https://github.com/anujkem/memory-game.git
                    sudo cp -r memory-game/* /var/www/html/
                    sudo systemctl restart nginx
                    EOF
                    """
                }
            }
        }
    }
}
