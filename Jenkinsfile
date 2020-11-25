#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                	sh 'docker pull owasp/zap2docker-weekly'
                    writeFile file: 'DAST.txt', text: 'DAST_report'
                    sh 'docker run -t owasp/zap2docker-weekly zap-baseline.py -t http://$(ip -f inet -o addr show docker0 | awk '{print $4}' | cut -d '/' -f 1):8080'

                }
            }
        }
	
		
		}
	}

		
	
	