#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
  
                	sh 'docker pull owasp/zap2docker-stable'
                	sh 'docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-weekly zap-baseline.py -t https://172.17.0.1:8080 -g gen.conf -r testreport.html'
                    
                
                }
            }
        }
	
		
		}
	}

		
	
	