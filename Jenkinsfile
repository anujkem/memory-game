pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'echo "Build Stage"'
                }
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
