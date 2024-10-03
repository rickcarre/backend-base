pipeline{
    agent any
    stages{
        stage('Etapa de Construccion de Aplicacion'){
            agent{
                docker{
                    image 'node:alpine3.20'
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
