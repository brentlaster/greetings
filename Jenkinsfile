#!groovy

def project_name

node {
		
	stage('Get source') {
	   checkout scm
	}
	stage('construct internal url') {
	   tokens = "${env.JOB_NAME}".tokenize('/')
	   project_name = tokens[1];
	   echo project_name
	   }
	 stage('mirror updates') {

	   echo env.WORKSPACE
	   echo internalGitURL+project_name
	 //  sh 'ssh -o StrictHostKeyChecking=no -l diyuser -p 29418 '+internalGitURL+' gerrit create-project FromGitHub/abc'
	    sshagent (credentials: ['local_gerrit']) {
			echo 'inside sshagent'	   
			sh 'ssh -o StrictHostKeyChecking=no -l diyuser -p 29418 '+internalGitURL+' gerrit create-project FromGitHub/abc'
	   }
	
	}
}	     
