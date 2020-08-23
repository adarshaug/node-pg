pipeline {
    environment {
	MAVEN_HOME = tool('MAVEN')
    registryCredential = 'dockerhub'
    }
	agent any

     stages {

	     stage('Cloning our Git') {
			steps {
				git changelog: false, poll: false, url: 'https://github.com/adarshaug/node-pg.git'
			}
		}

	     stage('Docker Build')	{
			steps{
				sh "docker build -t adarshaug/node-pg ."
				sh "docker push adarshaug/node-pg"
			}
	     }

     }
}
