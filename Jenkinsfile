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

        stage('clean1') {
            steps {
                sh '''
                ls
                touch paul
                pwd
                ls
                '''
            }
        }
    }
}
