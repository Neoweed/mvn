#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                    startZap(host: '127.0.0.1', port: 8090, zapHome: "/usr/local/zaproxy",sessionPath:"/usr/local/session.session") // Start ZAP at /opt/zaproxy/zap.sh, allowing scans on github.com
                	runZapCrawler(host: "http://localhost:8080")
                	archiveZap(failAllAlerts: 1, failHighAlerts: 0, failMediumAlerts: 0, failLowAlerts: 0, falsePositivesFilePath: "zapFalsePositives.json")
                }
            }
        }
	
		
		}
	}

		
	
	