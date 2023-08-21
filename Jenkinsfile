pipeline {
    agent  { label 'JDK18' }
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
                git url: 'https://github.com/anithack23/spring-petclinic.git', branch: 'main'
            }
        }
        
        stage('Build the code') {
            steps {
                sh script: 'mvn clean package'
            }
        }
        
        stage('Reporting and Archiving') {
            steps {
                junit testResults: 'target/surefire-reports/*.xml'
            }
        }
        
        // You can define more stages here if needed
    }
    
    post { 
        success {
            echo "Success"
        }
        failure {
            echo "Failure"
        }
    }
}
