pipeline {
  agent any
  stages {
    stage('Build hmtl doc') {
      agent { dockerfile true }
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
    stage('Create artifact of html'){
      steps {
        archiveArtifacts artifacts: '**/*.html', onlyIfSuccessful: true
        echo "Artifact created"
      }
    }
    stage ('Copy artifact to local'){
      steps {
        sh '''
        #!/bin/bash
        cp /Users/laurileskinen/.jenkins/workspace/Adoc/book.html /Users/laurileskinen/Documents/Programming/adocs_output
        '''
      }
    }
  }
}
