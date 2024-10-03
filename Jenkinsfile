pipeline{
    agent any
    environment{
        NPM_CONFIG_CACHE = "${WORKSPACE}/.npm"
    }
    stages{
        stage('Etapa de Construccion de Aplicacion'){
            agent{
                docker{
                    image 'node:alpine3.20'
                    reuseNode true
                }
            }
            stages{
                stage("Install"){
                    steps{
                        sh 'npm install'
                    }
                }
            }
        }
    }
}
