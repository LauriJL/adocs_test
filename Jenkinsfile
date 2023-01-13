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
      sh '''
      archiveArtifacts artifacts: 'book.html'
      '''
      echo "Post OK!"
    }
  }
}
