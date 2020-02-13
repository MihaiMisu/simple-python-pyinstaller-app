pipeline {
    agent any
    environment {
        // comment added
         APPLICATION = 'app'
         ENVIRONMENT = 'dev'
         MAINTAINER_NAME = 'jenkins'
         MAINTAINER_EMAIL = 'mmanoledev2majikan@gmail.com'
    }
    stages {
         stage('clone repository') {
             steps {
                 // cloning repo
                 checkout scm
             }
         }
         stage('Build Image') {
             steps {
                 script {
                     sshagent(credentials : ['jenkins-pem']) {
                        sh "echo pwd"
			sh "pwd"
                        sh 'ssh -t -t mmanole@10.183.57.15 -o StrictHostKeyChecking=no'
                        sh "echo pwd"
                        sh 'sudo -i -u root'
                        sh 'echo pwd'
                    }
                 }
             }
         }
     }
}
