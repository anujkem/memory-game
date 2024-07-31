pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/anujkem/memory-game.git'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh '''
                    sudo cp -r * /var/www/html/
                    sudo systemctl restart nginx
                    '''
                }
            }
        }
    }
}
