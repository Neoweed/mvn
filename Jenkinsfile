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

                    		sh "mvn clean install"
                    		timeout(time: 50, unit: 'SECONDS') 
                }
            }
			}
		}
	
		stage('print'){
			steps{
				sh 'sleep 30'
				sh 'echo "123"'
			}
		}
	}
}
		
	}
	}