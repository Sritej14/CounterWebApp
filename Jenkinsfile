pipeline {
      agent any

      
    stages {
        stage("Maven Build") {
            steps{
                sh 'mvn clean install'
            }
        }  
        stage("tomcat deployment") {
            steps{
                deploy adapters: [tomcat9(credentialsId: 'admin', path: '', url: 'http://65.2.137.187:8090')], contextPath: '/pipeline', war: '**/*.war'
            }
        }    
    }
}
