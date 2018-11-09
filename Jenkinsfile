pipeline {
agent any
tools {
  go 'localGo'
}
 ws("${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}/") {
            withEnv(["GOPATH=${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"]) {
                env.PATH="${GOPATH}/bin:$PATH
				}
}
stages{
  stage('Build'){
  steps { 
       sh 'go build hello-world.go'
      }
post {
  success { 
           echo 'Now Archiving...testing'
           archiveArtifacts artifacts :'**'
           }
       }
    }
	stage('Deploy'){
	  steps{
	  build job:'deploy to staging'
       } 
     }
   }
}
