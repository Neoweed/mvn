#!groovy
pipeline{
	agent any
	stages{
		stage('maven install and run echo'){
			parallel{
				stage('dep'){
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
	}