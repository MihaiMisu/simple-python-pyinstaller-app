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
	    steps {
                echo 'Deploying....'		
            }		
	    node {
		  def remote = [:]
		  remote.name = 'test'
		  remote.host = 'test.domain.com'
		  remote.user = 'root'
		  remote.password = 'password'
		  remote.allowAnyHosts = true
		  stage('Remote SSH') {
		    sshCommand remote: remote, command: "ls -lrt"
		    sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
		  }
		}
        }
    }
}
