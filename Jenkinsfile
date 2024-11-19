pipeline {
    agent any



    stages {
        stage('Build and Test') {
            steps {
                bat "mvn clean install"
                echo logSeparator
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}