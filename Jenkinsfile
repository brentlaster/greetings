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
			try {
			sh 'ssh -o StrictHostKeyChecking=no -l '+authorized_user+' -p 29418 '+internalGitURL+' gerrit create-project FromGitHub/'+project_name
			}
			catch (exc)
			{}			
			sh "git tag -a From_GitHub -m 'FromGitHub'"
            sh 'git push ssh://diyuser@localhost:29418/FromGitHub/greetings --tags'
	   }
	
	}
}	     
