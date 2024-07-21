pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('composer:latest').inside("-v ${env.WORKSPACE}:C:/workspace") {
                        bat 'cd C:\\workspace && composer install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    docker.image('composer:latest').inside("-v ${env.WORKSPACE}:C:/workspace") {
                        bat 'cd C:\\workspace && .\\vendor\\bin\\phpunit tests'
                    }
                }
            }
        }
    }
}