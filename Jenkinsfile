pipeline {
    agent any
    
    stages {
        stage('SCM') {
            steps {
               git changelog: false, poll: false, url: 'https://github.com/Sritej14/CounterWebApp.git'
            }
        }
         stage('Maven Build') {
            steps {
             sh 'mvn clean install'
            }
         }
           stage('Docker Build & Push') {
            steps {
                script{
              withDockerRegistry(credentialsId: 'admin', toolName: 'docker') {
             sh "docker build -t sritej09/myjava:1"
             sh "docker push"
            }
         }
    }
}
}
}
