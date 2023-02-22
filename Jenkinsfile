pipeline {
    agent any
    stages {
        stage('ssh') {
            steps {
                script{
                     
                    cleanWs()
                    sh "echo 'hello' >> file1.txt"
                    sh "echo 'hello' >> file2.txt"
                    sh "zip middleware_script_AWS.zp *"
                     
                    echo 'Local files.....'       
                    sh 'ls -l'
 
                    command='''
                        unzip -o -d ./ oneFile.zip
                        ls -l
                        date
                        cat /etc/os-release
                    '''
                         
 
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
