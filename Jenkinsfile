//Declerative pipeline
pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	//agent { docker { image 'node:13.8'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				//echo "Before sh"
				sh 'mvn --version'
				sh 'docker --version'
				//echo "After sh"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_IUD - $env.BUILD_ID"
				echo "JOB_NAME -$env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Compile') {
			steps {
				echo "Build"
				sh "mvn clean compile"
			}
		}

		stage('Test') {
			steps {
				echo "Test"
				sh "mvn test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Build Docker Image') {
			steps {
				echo "Build Docker Image"
				//"docker build -t vebhav/currency-exchange-devops:$env.BUILD_TAG"
				script {
					//docker.build("vebhav/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		}
		stage('Push Docker Image') {
			steps {
				echo "Integration Test"
				sh "mvn failsafe:integration-test failsafe:verify"
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
