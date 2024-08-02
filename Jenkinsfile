pipeline {
    agent any

    environment {
        DEPLOY_SERVER = '65.0.142.195'  // Your server's IP address
        SSH_CREDENTIALS_ID = 'bc7e84f4-244a-4656-867b-add45d838e05'  // Your SSH credentials ID
        DEPLOY_DIR = '/var/www/html'  // Directory on the server where files will be deployed
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the repository from GitHub
                git 'https://github.com/anujkem/memory-game.git'
            }
        }

        stage('Build') {
            steps {
                // For a simple HTML project, no build steps are needed
                echo 'No build steps needed for a simple HTML project'
            }
        }

        stage('Deploy') {
            steps {
                // Use SSH to copy files to the deployment server
                sshagent([env.SSH_CREDENTIALS_ID]) {
                    sh """
                    scp -o StrictHostKeyChecking=no -r * ubuntu@${env.DEPLOY_SERVER}:${env.DEPLOY_DIR}
                    """
                }
            }
        }
    }
}
