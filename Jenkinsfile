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
        stage('clear_cache') {
            steps {
                bat 'php artisan cache:clear'
                bat 'php artisan config:clear'
                bat 'php artisan view:clear'
                bat 'php artisan route:clear'
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
