#!groovy
pipeline{
	agent any
	options {
        timeout(time: 100, unit: 'SECONDS') 
    }
	stages{
		stage('maven install and dast'){
			parallel{
				stage('deploy'){
				steps{
					script{
                		withEnv(['JENKINS_NODE_COOKIE=dontkill']) {

                    		sh "mvn clean install || true"
                }
            }
			}
		}

		stage('DAST') {
            steps {
                script {
                    startZap(host: localhost, port: 8090, timeout:500, zapHome: "/opt/zaproxy") // Start ZAP at /opt/zaproxy/zap.sh, allowing scans on github.com
                	runZapCrawler(host: "http://localhost:8080")
                	archiveZap(failAllAlerts: 1, failHighAlerts: 0, failMediumAlerts: 0, failLowAlerts: 0, falsePositivesFilePath: "zapFalsePositives.json")
                }
            }
        }
	
		
		}
	}
}
		
	}
	