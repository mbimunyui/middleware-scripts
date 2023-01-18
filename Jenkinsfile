pipeline {
    agent any
    triggers {
  pollSCM('*/4 * * * *')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello '
                sleep 5
            }
        }
          stage('build') {
            steps {
                sh 'zip middleware_script.zp * -x Jenkinsfile'
                
            }
          }
            
            
        
          stage('test') {
            steps {
                echo 'test'
                sleep 5
            }
          } 
          stage('deploy') {
            steps {
                echo 'deploy'
                sleep 4
            }
        }
    }
}
