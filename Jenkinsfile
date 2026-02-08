pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                sh '''
                echo "Deploying Astra theme to EC2..."
                rsync -av --delete ./ ubuntu@51.20.51.166:/var/www/html/wordpress/wp-content/themes/astra/
                '''
            }
        }
    }
}

