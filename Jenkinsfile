def log(String message)
{
    echo "++++++++++++++++++++++++++ [ ${message} ]"
}

pipeline {
    agent any

    stages {
        stage('Build & Test') {
            steps {
                log('Building an testing...')

/*
                withMaven(
                    // Maven installation declared in the Jenkins "Global Tool Configuration"
                    maven: 'maven-3', // (1)
                    // Use `$WORKSPACE/.repository` for local repository folder to avoid shared repositories
                    mavenLocalRepo: '$WORKSPACE/.repository', // (2)
                    // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
                    // We recommend to define Maven settings.xml globally at the folder level using
                    // navigating to the folder configuration in the section "Pipeline Maven Configuration / Override global Maven configuration"
                    // or globally to the entire master navigating to  "Manage Jenkins / Global Tools Configuration"
                    mavenSettingsConfig: '0a2fb096-b75c-4c97-ac06-c1d16e913ccf' // (3)
                ) {
*/
                    // Run the maven build
                                        
//                    log('Cargado maven settings.xml')

                    bat "mvn clean install"
//                }
            }
        }
        stage('Deploy') {
            steps {
                log('Deploying to Cloudhub 2.0....')

/*
                withMaven(
                    // Maven installation declared in the Jenkins "Global Tool Configuration"
                    maven: 'maven-3', // (1)
                    // Use `$WORKSPACE/.repository` for local repository folder to avoid shared repositories
                    mavenLocalRepo: '$WORKSPACE/.repository', // (2)
                    // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
                    // We recommend to define Maven settings.xml globally at the folder level using
                    // navigating to the folder configuration in the section "Pipeline Maven Configuration / Override global Maven configuration"
                    // or globally to the entire master navigating to  "Manage Jenkins / Global Tools Configuration"
                    mavenSettingsConfig: '0a2fb096-b75c-4c97-ac06-c1d16e913ccf' // (3)
                ) {
*/                
                    // Run the maven build
                                        
//                    log('Cargado maven settings.xml')

                    bat "mvn clean deploy -DmuleDeploy -Pdev -DskipTests"
                }               
            }
        }
    }
}