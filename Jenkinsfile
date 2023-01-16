pipeline {
  agent none
  stages {
    stage('Build hmtl doc') {
      gent { dockerfile true }
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
  }
}
