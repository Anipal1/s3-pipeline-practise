pipeline {
        agent {
        label ("node1 || node2 || node3 || node4|| node5|| branch|| main || Jenkins-node || docker-agent || Jenkins-docker2 || preproduction || production")
    }

  options {
    buildDiscarder(logRotator(numToKeepStr: '1'))
    disableConcurrentBuilds()
    timeout (time: 60, unit: 'MINUTES')
    timestamps()
   }
    stages {

        stage('Setup parameters') {
            steps {
                script {
                    properties([
                        parameters([
                        
                        choice(
                            choices: ['Dev', 'Sanbox',  'Prod'], 
                            name: 'Environment'                   
                                ),

                        string(
                            defaultValue: 'anipal-001',
                            name: 'User',
                          description: 'Required to enter your name',
                            trim: true
                            ),

                        string(
                            defaultValue: 's4User',
                            name: 'DB-Tag',
                            description: 'Required to enter the image tag',
                            trim: true
                            ),

                        string(
                            defaultValue: 's4User',
                            name: 'UI-Tag',
                            description: 'Required to enter the image tag',
                            trim: true
                            ),
                           
                        string(
                            defaultValue: 's4User',
                            name: 'WEATHER-Tag',
                            description: 'Required to enter the image tag',
                            trim: true
                            ),
                        string(
                            defaultValue: 's4User',
                            name: 'AUTH-Tag',
                            description: 'Required to enter the image tag',
                            trim: true
                            ),

                        ])
                    ])
                }
            }
        }

    stage('permission') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }               




 stage('cleaning') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }

 stage('SonarQube analysis') {
            agent {
                docker {
                  image 'sonarsource/sonar-scanner-cli:4.7.0'
                }
               }
               environment {
        CI = 'true'
        //  scannerHome = tool 'Sonar'
        scannerHome='/opt/sonar-scanner'
    }
            steps{
                withSonarQubeEnv('Sonar') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }


stage('build-dev') {
            steps {
                sh '''
              cd UI
docker build -t devopseasylearning2021/s4-ui:$UITag .
cd -
cd DB
docker build -t devopseasylearning2021/s4-db:$DBTag .
cd -
cd auth 
docker build -t devopseasylearning2021/s4-auth:$AUTHTag .
cd -
cd weather 
docker build -t devopseasylearning2021/s4-weather:$WEATHERTag .
cd -

                '''
            }
        }               

stage('build-sanbox') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }                 

 stage('build-prod') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }              

stage('login') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }  

stage('push-to-dockerhub-dev') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }          

stage('push-to-dockerhub-sanbox') {
            steps {
                sh '''
                ls -h
                touch paul
                pwd
                '''
            }
        }  

stage('push-to-dockerhub-prod') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }  

stage('update helm charts-sanbox') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        } 

stage('update helm charts-dev') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }                  

stage('update helm charts-prod') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }       

stage('wait for argocd') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }       

stage('post build report (success, unstable, failure) on slack  development-alerts channel  and clean directory') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }
    }
        
  post {
    
    success {
      slackSend (channel: '#development-alerts', color: 'good', message: "The job was successfull")
    }

    failure {
      slackSend (channel: '#development-alerts', color: '#FF0000', message: "FAILURE: The job was NOT successfull")
    }
}      
        
}
