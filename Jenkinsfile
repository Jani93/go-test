pipeline {
agent any
tools {
  go 'localGo'
}
environment {
        GOPATH = "${pwd}"
        GOROOT = "/usr/bin/go"
    }
stages{
  stage('Build'){
  steps { 
        sh 'go version'
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
