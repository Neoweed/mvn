#!groovy
pipeline{
	agent any
	stages{
		parallel {
		stage('maven install'){
			steps{
				script{
                withEnv(['JENKINS_NODE_COOKIE=dontkill']) {
                    BUILD_ID=dontKillMe sh "mvn clean install"
                }
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
	}