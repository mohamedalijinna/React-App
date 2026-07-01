pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install') {
            steps {
                bat 'composer install --no-dev'
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

		stage('Deploy') {
			steps {
				bat '''
				ssh -o StrictHostKeyChecking=no ubuntu@13.61.151.127 ^
				"cd /var/www/project && \
				git pull origin main && \
				composer install --no-dev && \
				npm install && \
				npm run build && \
				php artisan migrate --force && \
				php artisan optimize && \
				sudo systemctl restart nginx && \
				sudo systemctl restart php8.2-fpm"
				'''
			}
		}
    }
}