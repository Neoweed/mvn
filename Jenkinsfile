#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
  
                	sh 'docker pull owasp/zap2docker-weekly'
                	sh 'docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-weekly zap-baseline.py -t https://172.17.0.1:8080|| true'
                    
                
                }
            }
        }
	
		
		}
	}

		
	
	