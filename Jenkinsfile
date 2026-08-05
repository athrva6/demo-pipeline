pipeline{
   agent any
     parameters{
         string(name: "VERSION", defaultValue: "1.0" , description: "varsion to deploy")
         choice(name: "ENVIRONMENT", choices: ['staging' , 'Production' ] , description: "Target")
         booleanParam(name: "SKIP_TEST" , defaultValue: false , description: "SKIP_TEST?")
     }
    stages {
        stage ('Build'){
                  steps{
                     echo 'Building'
                  sh "echo build with ${params.VERSION} to ${params.ENVIRONMENT}"
                  script{
                      if (params.SKIP_TEST){
                          echo 'test skipped by request'
                      }
                     }
                   }
           }
      }
}
