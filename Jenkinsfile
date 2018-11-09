pipeline {
agent any
tools {
  go 'localGo'
}
 environment {
export GOROOT=$(pwd)/go
export GOPATH=$(pwd)
    }
stages{
  stage('Build'){
  steps { 
  
       sh 'echo $GOROOT'
	          
	   
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
