pipeline {
  agent any
  stages {
    stage('Build Application') { 
      steps {
        bat 'mvn clean install'
      }
    }
 	stage('Test') { 
      steps {
        echo 'Test Appplication...' 
        bat 'mvn test'
      }
    }
 	
    stage('Deploy CloudHub') { 
    	      environment {
        chenv = "Sandbox"
      }
       steps {
        echo 'Deploying only because of code commit...'
        echo " deploying to  ${params.env} environent"
         echo " worker is  ${params.workerType}"
        bat 'mvn package deploy -DmuleDeploy -Dusername="kckc1502_1" -Dpassword="Chaitu@97" -Denvironment=Sandbox -DapplicationName=testattachmentsarc -DworkerType=Micro -Dworkers=1 -Dregion=us-east-2'
      }
    }
  }
}