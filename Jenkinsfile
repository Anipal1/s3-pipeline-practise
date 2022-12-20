pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                sh '''
                ls -h
                pwd
                '''
            }
        }
   
     }
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







}


