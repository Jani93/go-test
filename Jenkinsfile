pipeline {
agent any
tools {
  maven 'localGo'
}
stages{
  stage('Build'){
  steps { 
       sh 'go build'
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
