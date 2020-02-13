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
	    remote.name = 'test'
	    remote.host = 'test.domain.com'
	    remote.user = 'root'
	    remote.password = 'password'
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
