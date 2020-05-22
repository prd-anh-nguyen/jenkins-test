pipeline {
   agent any

   stages {
      stage('Init') {
          steps {
            echo "Banch name is: ${env.BRANCH_NAME}"
            echo "Banch target is: ${env.BRANCH_NAME}"
            echo "Banch change by: ${env.BRANCH_NAME}"   
          }
      } 
       
      stage('Build') {
         when {
            expression { return params.current_status == "closed" && params.merged == true }
         }
         steps {
            script {
                sh 'sh /var/lib/jenkins/run_deploy_danang.sh'
            }
            
         }
      }
   }
}
