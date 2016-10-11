#!groovy

node {
		
	stage('Get source') {
	   checkout scm
	}

	stage('mirror repo') {
	   echo internalGitURL
	   }
	stage('dump env') {
	   s = env.JOB_NAME
	   String[] parts = s.split("/")
	   String s2 = parts[1];
	   echo s2
	   }
}

