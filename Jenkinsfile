pipeline {
    agent any
    stages {
        stage('ssh') {
            steps {
                script{
                     
                 
                   
                    sh "zip middleware_script.zp *"
                  
                   
                         
 
                  // Copy file to remote server 
                  sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible',
                    transfers: [ sshTransfer(flatten: false,
                                 remoteDirectory: '',
                                             sourceFiles: '. *'
                    )])
                  ])
                   
                  
                     
                }
            }
        }
    }
         
}
