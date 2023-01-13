pipeline {
  agent { dockerfile true }
  stages {
    stage('Test') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          docker ps
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
  }
}
