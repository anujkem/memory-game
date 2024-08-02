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
                cp -r Jenkinsfile README.md anaconda.png bee.png chameleon.png cockatoo.png crocodile.png gorilla.png index.html macaw.png monkey.png piranha.png script.js sloth.png style.css tiger.png toucan.png /var/www/html/memory-game
                systemctl restart nginx
                '''
            }
        }
    }
}
