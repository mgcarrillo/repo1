pipeline {
	agent none
	environment {
		NODE_VER = '8.1.0'
	}
	stages {
		stage('Beginning') { agent any 
			environment {
				NEW_VAR = 'Stage'
			}
			steps {
				echo 'Hello World'
				sh 'echo $NODE_VER'
				echo "${env.ENV_VAR}"
			}
		}
		stage('Who Am I?') { agent any
			environment {
				NEW_VAR = 'Production'
			}
                	steps {
				echo "${env.ENV_VAR}"
				sh 'host -t TXT pgp.michaelholley.us | awk -F \'"\' \'{print $2}\''
			}
		}
	}
}
