#!groovy
library identifier: 'demo@jenkinscolor', retriever: modernSCM(
        [$class: 'GitSCMSource',
         remote: 'https://github.com/aruntothenew/demo'])
pipeline {
   agent any
    options{
       timestamps()
       ansiColor('xterm')
   }
   stages {
      stage('List All Images') {
         steps {
             script{
                    sh ''' docker image ls
                    '''
                    myscript.info("Successfully Executed")
                    def ret + sh(script: 'dooocker image ls', returnStatus: true)
                    myscript.warning(ret)
             }
         }
      }
      stage('Git Comit Id') {
          steps {
              script{
                  def gitId=sh(script:'git rev-parse HEAD', returnStdout: true)
                  myscript.gitCommitId(gitId)
              }
          }
      }
   }
}
