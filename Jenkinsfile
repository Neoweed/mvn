#!groovy
pipeline{
	agent any
	
		stages{
		stage('DAST') {
            steps {
                script {
                	sh 'docker pull owasp/zap2docker-stable'
                    sh 'docker run -v /var/lib/jenkins/workspace/test1/:/zap/wrk/ -t owasp/zap2docker-stable zap-baseline.py -t "http://172.17.0.1:8080" -w read.md || true'

                }
            }
        }
	
		
		}
	}

		
	
	