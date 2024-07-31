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
                    // Create the target directory if it doesn't exist
                    sh '''
                    if [ ! -d /var/www/html/memory-game ]; then
                        mkdir -p /var/www/html/memory-game
                    fi

                    # Copy files to the target directory
                    cp -r Jenkinsfile README.md anaconda.png bee.png chameleon.png cockatoo.png crocodile.png gorilla.png index.html macaw.png monkey.png piranha.png script.js sloth.png style.css tiger.png toucan.png /var/www/html/memory-game/
                    '''
                }
            }
        }
    }
}
