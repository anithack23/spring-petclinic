pipeline {
    agent  { label 'JDK11' }
    options {
        timeout(time: 1, unit: 'SECONDS')
        retry(2)     
        }
    triggers{
      cron ('0 * * * *')
     }
    stages {
        stage('Source code') {
            steps {
                git url: 'https://github.com/anithack23/spring-petclinic.git', branch:'main'
            }
       stage('Build the code'){
             setps{
                sh script: 'mvn clean package'


      stage('Reporting and Archiving'){
        setps{
            junit testResults : 'target/surefire-reports/*.xml'
     
     

      }
       }
         }         
         }

        }
       }


post{ 
   success{
    //send the success email

    echo "Success"
}
    unsuccessful{
     echo "Failure

}
}


}
