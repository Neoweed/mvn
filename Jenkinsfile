#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
  
                	sh 'docker pull owasp/zap2docker-weekly'
                	sh 'mkdir -p $(pwd)/zap'
                	sh 'mkdir -p $(pwd)/zap/wrk'
                	sh 'chmod a+r+w $(pwd)/zap/wrk/'
                	sh 'docker run -v $(pwd)/zap/wrk/ -t owasp/zap2docker-weekly zap-baseline.py -t https://172.17.0.1:8080 -r test.html || true'
                    
                
                }
            }
        }
	
		
		}
	}

		
	
	