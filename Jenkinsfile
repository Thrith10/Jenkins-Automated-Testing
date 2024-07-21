pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('composer:latest').inside('-v ${env.WORKSPACE}:${env.WORKSPACE}') {
                        sh 'composer install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    docker.image('composer:latest').inside('-v ${env.WORKSPACE}:${env.WORKSPACE}') {
                        sh './vendor/bin/phpunit tests'
                    }
                }
            }
        }
    }
}
