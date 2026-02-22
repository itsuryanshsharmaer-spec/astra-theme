pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                sh '''
                echo "Deploying Astra theme to EC2..."

                rsync -avz --delete \
                  --exclude='.git' \
                  --exclude='Jenkinsfile' \
                  --no-perms --no-owner --no-group \
                  -e "ssh -i /var/lib/jenkins/.ssh/jenkins_deploy_key -o StrictHostKeyChecking=no" \
                  ./ ubuntu@13.50.160.64:/var/www/html/wordpress/wp-content/themes/astra/

                echo "Deployment completed successfully."
                '''
            }
        }
    }
}
