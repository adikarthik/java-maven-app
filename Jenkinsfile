pipeline {
	agent any
	stages {
	    stage ('clean up') {
	        steps {
	            cleanWs()
	        }
	    }
	    stage ('clone') {
			steps {
				sh 'git clone https://github.com/BinduPhalguna/java-maven-app'
			}
		
		}
		stage ('build') {
			steps {
			    
				    sh 'mvn clean install -DskipTests'
			    }
			}
		
		}
		stage ('test') {
			steps {
			  
			        sh 'mvn test'
			    }
			}
			post {
				always {
				  
					    junit 'target/surefire-reports/*.*xml'
				    }
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
}
