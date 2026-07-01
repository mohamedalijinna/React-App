pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Composer Install') {
            steps {
                bat 'composer install'
            }
        }

        stage('Install Node Modules') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Assets') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'php artisan test'
            }
        }

        stage('Optimize Laravel') {
            steps {
                bat 'php artisan optimize'
            }
        }

    }

    post {

        success {
            echo 'Build Successful!'
        }

        failure {
            echo 'Build Failed!'
        }

    }

}