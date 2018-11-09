pipeline {
agent any
tools {
  go 'localGo'
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
environment {
        GOPATH = "${pwd}"
    }
	stage('Deploy'){
	  steps{
	  build job:'deploy to staging'
       } 
     }
   }
}
