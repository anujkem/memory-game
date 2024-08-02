pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/anujkem/memory-game.git', credentialsId: '41cd08d2-aea8-4e0f-acd8-44cde6931070'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                sudo cp -r * /var/www/your_project
                sudo systemctl restart nginx
                '''
            }
        }
    }
}
