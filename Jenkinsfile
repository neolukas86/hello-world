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

                configFileProvider([configFile(fileId: '0a2fb096-b75c-4c97-ac06-c1d16e913ccf', variable: 'maven')]) {
                    log('Cargando File Provider...')
                    log(${env.maven.servers})
                    bat "mvn test"
                    log('End File Provider!')
                }                
            }
        }
        stage('Deploy') {
            steps {
                log('Deploying....')

                bat "mvn clean deploy -DmuleDeploy -Pdev -DskipTests"
            }
        }
    }
}