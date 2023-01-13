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
  }
  post {
        always {
            archiveArtifacts artifacts: '**', onlyIfSuccessful: true
        }
    }
}
