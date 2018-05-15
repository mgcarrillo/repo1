pipeline {
	agent none
	environment {
		NODE_VER = '8.1.0'
	}

        // set global options - for example timeout for input responses	
	// or skip checking out code every time
	/*
	options {
		// skipDefaultCheckout()
		// timeout(time: 1, unit: 'DAYS')
	}

	// tools to use - node, maven docker, etc
	tools {
	}

	// post build steps
	post {
		success {

		}
		// failure, aborted, etc 
	}
	//

	stages {
		stage('Beginning') { agent any 
			environment {
				DEPLOY_VERSION = 'Stage'
			}
			steps {
				echo 'Hello World'
				sh 'echo $NODE_VER'
				echo "${env.DEPLOY_VERSION}"
			}
		}
		stage('Who Am I?') { agent any
			environment {
				DEPLOY_VERSION = 'Production'
			}
                	steps {
				echo "${env.DEPLOY_VERSION}"
				sh 'host -t TXT pgp.michaelholley.us | awk -F \'"\' \'{print $2}\''
			}
		}
		stage('Deploy to stage?') { agent none
		  	when {
				branch 'stage'
				environment name: 'NODE_VER', value: '8.1.0'
				// can also use anyof
			}
			steps {
				input 'Deploy to stage?'
				//input message: 'Where do you want to go', parameters: [choice(choices: "Yes\nNo\nMaybe", description: '', name: 'Deploy')]
			}
		}
		stage('Parallel') {
			failFast true  // fail immediately if all failed
			parallel {
				stage('Build1') { agent any
					steps {
						echo "Its me"
					}
				}
				stage('Build2') { agent any 
					steps {
						echo "Its not me"
					}
				}
			}
		}
	}
}
