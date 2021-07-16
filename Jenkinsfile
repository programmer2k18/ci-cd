pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '/usr/local/bin/composer install'
            }
        }
        stage('init') {
            steps {
                echo 'php artisan key:generate'      
            }    
        }
        stage('Test') {
            steps {
                echo 'vendor/bin/phpunit tests/Feature'
            }
        }
        stage('Deploy') {
            steps {
               echo 'php artisan serve --port=9999'
            }
        }
    }
}
