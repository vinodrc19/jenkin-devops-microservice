//Declerative pipeline
pipeline {
	//agent any
	//agent { docker { image 'maven:3.6.3'} }
	agent { docker { image 'node:13.8'} }
	stages {
		stage('Build') {
			steps {
				echo "Before sh"
				//sh 'mvn --version'
				sh 'node --version'
				echo "After sh"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo "runs always"
		}
		success {
			echo "runs when successfull"
		}
		failure {
			echo "runs when fails"
		}
	}
}
