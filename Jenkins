pipeline {
    agent any
    
    environment {
        DEPLOY_SERVER = '65.0.142.195'
        SSH_CREDENTIALS_ID = 'your-ssh-credentials-id'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/anujkem/memory-game.git'
            }
        }
        
        stage('Build') {
            steps {
                // Add your build steps here
                sh 'echo "Building the project..."'
            }
        }
        
        stage('Deploy') {
            steps {
                sshagent([env.SSH_CREDENTIALS_ID]) {
                    sh """
                    ssh -o StrictHostKeyChecking=no ubuntu@${env.DEPLOY_SERVER} << EOF
                    cd /var/www/html
                    git pull https://github.com/anujkem/memory-game.git
                    sudo systemctl restart nginx
                    EOF
                    """
                }
            }
        }
    }
}
