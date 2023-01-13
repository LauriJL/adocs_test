pipeline {
  agent { dockerfile true }
  stages {
    stage('Test') {
      steps {
        echo 'workspace: ${WORKSPACE}'
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
  }
}
