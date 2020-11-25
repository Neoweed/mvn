#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                	sh 'docker pull owasp/zap2docker-weekly'
                    writeFile file: 'DAST.txt', text: 'DAST_report'
                    sh 'docker run -p 8090:8090 -t owasp/zap2docker-weekly zap-baseline.py -t https://github.com/Neoweed/pplscn'

                }
            }
        }
	
		
		}
	}

		
	
	