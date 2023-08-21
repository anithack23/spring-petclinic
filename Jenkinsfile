node('JDK11') {
    stage('sourceCode') {
       //get the code from git repos
          git branch: 'main', url: 'https://github.com/anithack23/spring-petclinic.git'
    }
    stage('Build the code') {
            sh 'mvn clean package'
     
     
    } 

    stage('Archiving and Test Results'){
            junit '**/surefire-reports/*.xml'
            archiveArtifacts artifacts: '**/*.war', followSymlinks: false


          
    }
}
