pipeline{
         agent {
            label 'pipeline-agents'
               }
 
         stages {
              stage(" checkout the code "){
                  steps{
                      checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/cloud-dev-user/javademo.git']])
                  }
              }
              stage("build") {
            steps {
                sh 'mvn package'
                   }
                }
         }  
         post {
  always {
    cleanWs()
  }
}
         }
