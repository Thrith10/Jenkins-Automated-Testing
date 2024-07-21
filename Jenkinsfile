pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'composer install'
            }
        }
        stage('Test') {
            steps {
                bat '.\\vendor\\bin\\phpunit tests'
            }
        }
    }
}