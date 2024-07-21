pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Convert the Windows path to Unix-style
                    def workspaceUnixPath = env.WORKSPACE.replaceAll('C:', '/c').replaceAll('\\\\', '/')
                    
                    docker.image('composer:latest').inside("-v ${workspaceUnixPath}:${workspaceUnixPath}") {
                        sh "cd ${workspaceUnixPath} && composer install"
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Convert the Windows path to Unix-style
                    def workspaceUnixPath = env.WORKSPACE.replaceAll('C:', '/c').replaceAll('\\\\', '/')
                    
                    docker.image('composer:latest').inside("-v ${workspaceUnixPath}:${workspaceUnixPath}") {
                        sh "cd ${workspaceUnixPath} && ./vendor/bin/phpunit tests"
                    }
                }
            }
        }
    }
}
