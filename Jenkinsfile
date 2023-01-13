pipeline {
  agent { dockerfile true }
  stages {
    stage('Test') {
      steps {
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
  }
}
