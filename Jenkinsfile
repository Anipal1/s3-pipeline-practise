pipeline {
        agent {
        label ("node1 || node2 || node3 || node4|| node5|| branch|| main || Jenkins-node || docker-agent || Jenkins-docker2 || preproduction || production")
    }

  options {
    buildDiscarder(logRotator(numToKeepStr: '20'))
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
cat <<EOF > check.sh
#! /bin/bash 
USER=${User}
cat permission.txt | grep -i $USER
if 
[[ $? -eq 0 ]]
then 
echo "You have permission to run this job"
else 
echo "You DON'T have permission to run this job"
exit 1
fi 
EOF
bash -x check.sh
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

 stage('sonarqube') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                '''
            }
        }

stage('build-dev') {
            steps {
                sh '''
                ls
                touch paul
                pwd
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
                ls
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
