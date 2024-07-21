pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('composer:latest').inside('-v /c/Users/renes/AppData/Local/Jenkins/.jenkins/workspace/Jenkins Automated Testing:/workspace') {
                        sh 'cd /workspace && composer install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    docker.image('composer:latest').inside('-v /c/Users/renes/AppData/Local/Jenkins/.jenkins/workspace/Jenkins Automated Testing:/workspace') {
                        sh 'cd /workspace && ./vendor/bin/phpunit tests'
                    }
                }
            }
        }
    }
}
