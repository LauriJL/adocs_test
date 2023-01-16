pipeline {
  agent { dockerfile true }
  stages {
    stage('Build hmtl doc') {
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
    stage ('Copy artifact'){
      steps {
        sh '''
        cp ${JENKINS_HOME}/jobs/workspace/Adoc/**.html /Users/laurileskinen/Documents/Programming/adocs
        '''
      }
    }
  }
}
