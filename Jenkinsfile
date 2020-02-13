pipeline {
    agent any
    environment {
        // comment added
         APPLICATION = 'app'
         ENVIRONMENT = 'dev'
         MAINTAINER_NAME = 'jenkins'
         MAINTAINER_EMAIL = 'jenkins@email.com'
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
                        sh 'ssh -t -t ubuntu@xx.xxx.xx.xx -o StrictHostKeyChecking=no'
                        sh "echo pwd"
                        sh 'sudo -i -u root'
                        sh 'cd /opt/docker/web'
                        sh 'echo pwd'
                    }
                 }
             }
         }
     }
}
