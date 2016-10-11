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
	   echo s
	   }
}

