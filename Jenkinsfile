pipeline {
    environment {
	MAVEN_HOME = tool('MAVEN')
    registryCredential = 'dockerhub'
    }
	agent any

     stages {

	     stage('Cloning our Git') {
			steps {
				git changelog: false, poll: false, url: 'https://github.com/adarshaug/simple-webapp.git'
			}
		}

	     stage('Docker Build')	{
			steps{
				sh "docker build -t adarshaug/simple-webapp ."
				sh "docker push adarshaug/simple-webapp"
			}
	     }

     }
}