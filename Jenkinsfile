def log(String message)
{
    echo "++++++++++++++++++++++++++ [ ${message} ]"
}

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                log('Building....')
                
                bat "mvn clean install -DskipTests"
            }
        }
        stage('Test') {
            steps {
                log('Testing....')
                
                //bat "mvn test"
            }
        }
        stage('Deploy') {
            steps {
                log('Deploying....')

                bat "mvn clean deploy -DmuleDeploy -Pdev"
            }
        }
    }
}