pipeline {
    agent any

    environment {
        MULE_SETTINGS = 'C:/Users/lucas.sanchez/.m2/settings.xml'
    }

    stages {
        stage('Build and Test') {
            steps {
                sh "mvn clean install --settings ${MULE_SETTINGS}"
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