pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
	    def remote = [:]
	    remote.name = 'mmanole'
	    remote.host = '10.183.57.15'
	    remote.user = 'mmanole'
	    remote.password = 'mmMajikan20@0'
	    remote.allowAnyhosts = true
	    stage('Remote SSH') {
		sshCommand remote: remote, command: "ls"
		}

            steps {
                echo 'Deploying....'		
            }
        }
    }
}
