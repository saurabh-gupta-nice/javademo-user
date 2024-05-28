pipeline{
         agent {
            label 'pipeline-agents'
               }
         parameters {string defaultValue: 'master', name: 'branch_name'}
         stages {
              stage(" checkout the code "){
                  steps{
                      git branch: "$branch_name", url: 'https://github.com/saurabh-gupta-nice/javademo-user.git'
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
