pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/anujkem/memory-game.git'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Replace this path with the actual path to your Nginx root directory
                    sh '''
                    sudo cp -r * /var/www/html/memory-game/
                    sudo systemctl restart nginx
                    '''
                }
            }
        }
    }
}
