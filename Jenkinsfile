pipeline {
    agent any
    stages {
        stage('ssh') {
            steps {
                script{
                     
                    cleanWs()
                   
                    sh "zip middleware_script_AWS.zp *"
                  
                   
                         
 
                  // Copy file to remote server 
                  sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible',
                    transfers: [ sshTransfer(flatten: false,
                                 remoteDirectory: '',
                                             sourceFiles: 'zip middleware_script_AWS.zp'
                    )])
                  ])
                   
                  // Execute commands
                  sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible',
                    transfers: [ sshTransfer(execCommand: command    )])])
                     
                }
            }
        }
    }
         
}
