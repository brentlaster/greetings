#!groovy

node {
		
	stage('Get source') {
	   checkout scm
	}

	stage('mirror repo') {
	   echo internalGitURL
	   }
	stage('dump env') {
	   bat 'set > env.txt'
	   readFile('env.txt').split("\r?\n").each{
	   	println it
	   }
	}
}

