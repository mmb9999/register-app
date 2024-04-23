pipeline {
    agent{ label 'jenkins-agent'}
	tools {
	    jdk 'Java17'
	    maven 'Maven3'		
	}
	stages{
	   stage("Cleanup Workspace"){
	     steps {
		cleanws()
	     }
	   }
	   stage("Checkout from scm"){
		   steps {
		   git branch : 'main' , credentialsId : 'github' , url : 'https://github.com/mmb9999/register-app.git'
		   }
	   }
	  stage("Build Application") {
		  steps {
	          sh 'mvn clean package'
		  }
	  }
	  stage("Test Application") {
		  steps {
		  sh 'mvn test'
		  }
	  }
    }
}
