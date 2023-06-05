pipeline {
 agent none
 stages {
   stage('Upstream pipeline running by me') {
    steps {
     script {
       node() {
         checkout scm
         build job: 'first_down_job', propagate: true,
         parameters: [[$class: 'StringParameterValue', name: 'git_url_k', value: sh(returnStdout: true, script: 'git config remote.origin.url').trim()],
		      [$class: 'StringParameterValue', name: 'branch_name_k', value: env.BRANCH_NAME]
		 ]
       }
     }
   }
 }
}
}
