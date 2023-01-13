pipeline {
  agent { dockerfile true }
  stages {
    stage('Build hmtl doc') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
          cp /Users/laurileskinen/.jenkins/workspace/Adoc /Users/laurileskinen/Documents/Programming/adocs_temp
        '''
      }
    }
  }
}
