    pipeline {
        agent {
            docker {
                image 'node:16-buster-slim'
                args '-p 3000:3000'
            }
        }
        stages {
            stage('Build') {
                steps {
                    sh 'npm install'
                }
            }
            stage('Test') {
                steps {
                    sh './jenkins/scripts/test.sh'
                }
            }
            
	
        stage('Manual Aproval') {
            steps {
                input message :'Lanjut ke tahap Deployment? (pilih proccess untuk lanjut)'

            }
        }

	stage('Deploy') { 
                steps {
                    input message: 'Lanjut Proses Deploy? (Klik "Proceed" untuk melanjutkan deployment)'
		    sh './jenkins/scripts/deliver.sh' 
                    sleep time : 1, unit :'MINUTES' 
                }
            }
        }
    }
