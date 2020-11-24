#!groovy
pipeline{
	agent any
	stages{
		stage('maven install'){
			steps{
				script{
                withEnv(['JENKINS_NODE_COOKIE=dontkill']) {
                    sh "mvn clean install"
                }
			}
		}
		stage('print'){
			steps{
				sh 'echo "123"'
			}
		}
		
	}
	}