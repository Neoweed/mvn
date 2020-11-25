#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                	sh 'docker pull owasp/zap2docker-stable'
                    writeFile file: 'DAST.txt', text: 'DAST_report'
                    sh 'docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-stable zap-baseline.py \
    -t "http://172.17.0.1:8080" -g gen.conf -r testreport.html || true'

                }
            }
        }
	
		
		}
	}

		
	
	