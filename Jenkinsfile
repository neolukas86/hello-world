def log(String message)
{
    echo "++++++++++++++++++++++++++ [ ${message} ]"
}

pipeline {
    agent any

    stages {
        stage('Build and Test') {
            steps {
                log('Building and Testing....')
                log('dtd.anypoint.platform.client_id: ' + env.dtd.anypoint.platform.client_id)
                
                bat "mvn clean install"
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