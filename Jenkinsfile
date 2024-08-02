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
                sh '''
                sudo cp -r * /var/www/html/memory-game
                sudo systemctl restart nginx
                '''
            }
        }
    }
}
