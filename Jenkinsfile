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
                    cp -r * /var/www/html/
                    systemctl restart nginx
                    '''
                }
            }
        }
    }
}
