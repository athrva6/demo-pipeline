pipeline {
    agent any
    parameters {
        string(name: 'VERSION', defaultValue: '1.0', description: 'Version to deploy')
        choice(name: 'ENVIRONMENT', choices: ['staging', 'production'], description: 'Target')
        booleanParam(name: 'SKIP_TESTS', defaultValue: false, description: 'Skip tests?')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
                sh "echo Deploying version ${params.VERSION} to $(params.ENVIRONMENT}"
                script{ if (params.SKIP_TESTS){ echo 'test skipped by request' } }
              }
        }
    }
}

