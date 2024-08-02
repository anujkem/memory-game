pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-repository.git'
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
