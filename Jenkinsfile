pipeline {
    agent main
    stages {
        stage('Hello') {
            steps {
                sh '''
                ls-h 
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
                            choices: ['Dev', 'QA', 'Preprod', 'Prod'], 
                            name: 'Environment'
                                 
                                ),


                          string(
                            defaultValue: 'develop',
                            name: 'Area',
			    description: 'Enter the image Tag to deploy',
                            trim: true
                            ),
                        ])
                    ])
                }
            }
        }







}


