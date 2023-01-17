pipeline {
  agent { dockerfile 
         {filename 'Dockerfile'}
        }
  stages {
    stage('Build hmtl doc') {  
      steps {
        echo "Current workspace is $WORKSPACE"
        echo "Build number is ${currentBuild.number}"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
    stage('Create artifact of html'){
      steps {
        archiveArtifacts artifacts: '**/*', excludes: '**/Jenkinsfile, **/Dockerfile, **/*.adoc', onlyIfSuccessful: true
        echo "Artifact created"
      }
    }
  }
}
