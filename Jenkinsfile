pipeline {
  agent { dockerfile true }
  stages {
    stage('Test') {
      steps {
        sh '''
          asciidoctor --version
          git --version
          curl --version
        '''
      }
    }
  }
}
