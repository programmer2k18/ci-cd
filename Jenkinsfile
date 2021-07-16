pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'composer install'
            }
        }
        stage('init') {
            steps {
                sh 'php artisan key:generate'      
            }    
        }
        stage('Test') {
            steps {
                sh 'vendor/bin/phpunit tests/Feature'
            }
        }
        stage('Deploy') {
            steps {
               sh 'php artisan serve --port=9999'
            }
        }
    }
}
