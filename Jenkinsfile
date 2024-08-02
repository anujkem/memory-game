pipeline {
    agent any

    environment {
        DEPLOY_SERVER = '65.0.142.195'
        SSH_CREDENTIALS_ID = 'bc7e84f4-244a-4656-867b-add45d838e05'
        DEPLOY_DIR = '/var/www/html'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anujkem/memory-game.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build steps needed for a simple HTML project'
            }
        }

        stage('Deploy') {
            steps {
                sshagent([env.SSH_CREDENTIALS_ID]) {
                    sh """
                    scp -o StrictHostKeyChecking=no -r * ubuntu@${env.DEPLOY_SERVER}:${env.DEPLOY_DIR}
                    """
                }
            }
        }
    }
}
