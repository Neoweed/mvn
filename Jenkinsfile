#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                	sh 'docker pull owasp/zap2docker-weekly'
                    writeFile file: 'DAST.txt', text: 'DAST_report'
                    sh 'docker run -p 8090:8090 -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-weekly zap-baseline.py -t "http://172.17.0.1:8080" -r testreport.html || true'

                }
            }
        }
	
		
		}
	}

		
	
	