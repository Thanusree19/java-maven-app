pipeline {
	agent any
	tools {
		maven 'maven'
	      }
	stages {
	                stage ('build') {
			steps {
				sh 'mvn clean install -DskipTests'
			}
		
		}
		stage ('compile') {
			steps {
				sh 'mvn compile'
			}
			post {
				always {
					junit 'target/surefire-reports/*.*xml'
				}
			}
		}
		stage ('run') {
			steps {
				sh './scripts/deliver.sh'
			}
		
			
		}
	}
}