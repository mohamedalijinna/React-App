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
        sshPublisher(
            publishers: [
                sshPublisherDesc(
                    configName: 'aws-ec2',
                    transfers: [
                        sshTransfer(
                            execCommand: '''
set -x

pwd

whoami

ls -la

cd /var/www/html/React-App || exit 1

pwd

git status

git pull origin main

composer install --no-dev

npm install

npm run build

php artisan migrate --force

php artisan optimize

sudo systemctl restart nginx

sudo systemctl restart php8.2-fpm
'''
                        )
                    ]
                )
            ]
        )
    }
}
    }
}