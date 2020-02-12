pipeline{
    agent none
    stages{
        stage('Build'){
            agent{
                docker{
                    image 'sudo python:2-alpine'
                }
            }
            steps{
                sh 'sudo python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
        stage('Test'){
            agent{
                docker{
                    image 'qnib/pytest'
                } 
            }
            steps{
                sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
            }
            post{
                always{
                    junit 'test-reports/results.xml'
                }
            }
        }
    }
}
