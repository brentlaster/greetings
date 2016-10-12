#!groovy

def project_name

node {
		
	stage('Get source') {
	   checkout scm
	}
	stage('construct internal url') {
	   tokens = "${env.JOB_NAME}".tokenize('/')
	   project_name = tokens[2];
	   echo project_name
	   }
	 stage('mirror updates') {
	   echo url
	   echo env.WORKSPACE
	  
	   sshagent (credentials: ['158a93e0-cdfc-4b02-aeab-2b46182ca80e']) {
			sh 'ssh -p 29418 'internalGitURL' gerrit create-project FromGitHub/'project_name
	   }
	
	}
}	     
