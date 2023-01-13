pipeline {
  agent { dockerfile true }
  stages {
    stage('Test') {
      steps {
        sh '''
          asciidoctor --version
          docker run asciidoctor/docker-asciidoctor:lts
          asciidoctor book.adoc
        '''
      }
    }
  }
}
