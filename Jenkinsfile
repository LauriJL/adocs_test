pipeline {
  agent { dockerfile true }
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
        archiveArtifacts artifacts: '**/*.html', onlyIfSuccessful: true
        echo "Artifact created"
      }
    }
    stage ('Copy artifact to local'){
      agent any
      steps {
        sh '''
        #!/bin/bash
        cp /Users/laurileskinen/.jenkins/workspace/Adoc/book.html /Users/laurileskinen/Documents/Programming/adocs_output
        '''
      }
    }
  }
}
