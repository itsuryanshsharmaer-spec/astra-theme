pipeline {
    agent any

    stages {
        stage('Deploy Astra Theme') {
            steps {
                sh '''
                sudo rsync -av --delete ./ /var/www/html/wordpress/wp-content/themes/astra/
                sudo chown -R www-data:www-data /var/www/html/wordpress/wp-content/themes/astra
                sudo systemctl reload apache2
                '''
            }
        }
    }
}
