pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'composer install'
            }
        }
        stage('init') {
            steps {
                bat 'php artisan key:generate'      
            }    
        }
        stage('Test') {
            steps {
                bat 'vendor/bin/phpunit tests/Feature'
            }
        }
        stage('Deploy') {
            steps {
               bat 'php artisan serve --port=9999'
            }
        }
    }
}
