#!groovy
pipeline{
	agent any
	stages{
		stage('maven install'){
			steps{
				sh'mvn clean install'
			}
		}
		stage('print'){
			steps{
				sh 'echo "123"'
			}
		}
		
	}
	}