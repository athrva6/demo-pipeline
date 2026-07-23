pipeline {
    agent any
    parameters {
        choice(name: 'ENVIRONMENT', choices: ['staging', 'production'], description: 'Target')
    }
    stage('Approve') {
            when {
                expression { params.ENVIRONMENT == 'production' }
            }
            steps {
                input message: 'Deploy to production?'
            }
        }
        stage('Deploy') {
            steps {
                sh "echo Deploying to ${params.ENVIRONMENT}"
            }
        }


}

       
