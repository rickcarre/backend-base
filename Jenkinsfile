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
                stage("test"){
                    steps{
                        sh 'npm run test'
                    }
                }
                stage("Build"){
                    steps{
                        sh 'run build'
                    }
                } 
            }
            stages{
                stage("Construccion imagen docker"){
                    steps{
                        sh 'docker build - t app .'
                        sh 'docker tag backend-base us-central1-docker.pkg.dev/expertis-classroom/docker-repository/backend-base:RCR'
                    }
                }
            }
        }
    }
}
