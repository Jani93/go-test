pipeline {
agent any
tools {
  go 'localGo'
}
 environment {
export PATH=$(pwd)/go/bin:$PATH
export GOROOT=$(pwd)/go
export GOPATH=$(pwd)
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
