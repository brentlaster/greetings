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
	   sshagent (credentials: ['52c76d99-567b-40ca-947b-971297998997']) {
			echo 'inside sshagent'	   
			sh 'ssh -p 29418 'internalGitURL' gerrit create-project FromGitHub/abc'
	   }
	
	}
}	     
