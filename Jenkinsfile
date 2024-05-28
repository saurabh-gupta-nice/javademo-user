pipeline{
         agent {
            label 'pipeline-agents'
               }
 
         stages {
              stage(" checkout the code "){
                  steps{
                      checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/saurabh-gupta-nice/javademo-user.git']])
                  }
              }
              stage("build") {
            steps {
                sh 'mvn package'
                   }
                }
         stage("Notify") {
                  steps {
                           echo "Build success"
                  }
         }
         }  
         post {
  always {
    cleanWs()
  }
}
         }
