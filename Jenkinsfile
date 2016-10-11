#!groovy

node {
		
	stage('Get source') {
	   checkout scm
	}

	stage('mirror repo') {
	   echo internalGitURL
	   }
	stage('construct internal url') {
	   s = env.JOB_NAME
	   String[] parts = s.split("/")
	   String url = internalGitURL + parts[1];
	   
	   }
}

