pipeline {
  agent { dockerfile true }
  stages {
    stage('Build hmtl doc') {  
      steps {
        echo "Current workspace is $WORKSPACE"
        echo "Build number is ${currentBuild.number}"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
  }
}
