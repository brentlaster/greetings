#!groovy

node {
		
	stage('Get source') {
	   checkout scm
	}
	stage('construct internal url') {
	   s = env.JOB_NAME
	   String[] parts = s.split("/")
	   String url = internalGitURL + parts[1];
	   echo url
	   }
}

