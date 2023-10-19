//Declerative pipeline
pipeline {
	agent any
	//agent {
	//	docker {
	//		image "maven:3.6.0-jdk-8"
	//	}
	//}
	//agent { 
		//label "docker" { 
		//dockerContainer {	
		//	docker pull maven:3.6.3
		//	//image 'maven:3.6.3'
		//	//image 'maven:3.6.0-jdk-8'
		//} 
	//}
	stages {


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
		//failure {
		//	echo "runs when fails"
		//}
	}
}
