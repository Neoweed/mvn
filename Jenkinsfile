#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                	sh'sleep 30'
                    startZap(host: '127.0.0.11', port: 8090, zapHome: "/opt/zaproxy",allowedHosts:['github.com']) // Start ZAP at /opt/zaproxy/zap.sh, allowing scans on github.com
                	runZapCrawler(host: "https://github.com/Neoweed/pplscn")
                	archiveZap(failAllAlerts: 1, failHighAlerts: 0, failMediumAlerts: 0, failLowAlerts: 0, falsePositivesFilePath: "zapFalsePositives.json")
                }
            }
        }
	
		
		}
	}

		
	
	