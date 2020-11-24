#!groovy
pipeline{
	agent any
	options {
        timeout(time: 100, unit: 'SECONDS') 
    }
	stages{
		stage('maven install and run echo'){
			parallel{
				stage('dep'){
				steps{
					script{
                		withEnv(['JENKINS_NODE_COOKIE=dontkill']) {

                    		sh "mvn clean install"
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