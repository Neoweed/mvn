#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                	sh 'docker pull owasp/zap2docker-stable'
                	sh 'chmod a+r $(pwd)'
                	sh 'chmod a+w $(pwd)'
                	sh 'docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-stable zap-baseline.py -t http://172.17.0.1:8080 -r DAST_report.html || true'
                    publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/test2', reportFiles: 'DAST_report.html', reportName: 'HTML Report', reportTitles: ''])
                
                }
            }
        }
	
		
		}
	}

		
	
	