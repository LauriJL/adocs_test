pipeline {
  agent { dockerfile true }
  stages {
    stage('Build hmtl doc') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          whoami
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
  }
}
