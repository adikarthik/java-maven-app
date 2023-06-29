pipeline {
	agent any
	tools {
        maven 'm1' 
    }
	stages {
		stage ('build') {
			steps {
				sh 'mvn clean install -DskipTests'
			}
		
		}
		stage ('test') {
			steps {
				sh 'mvn test'
			}
			
		}
		stage ('run') {
			steps {
				sh './scripts/deliver.sh'
			}
		
		}
	}
}
