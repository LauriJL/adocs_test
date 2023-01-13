pipeline {
  agent { dockerfile true }
  stages {
    stage('Build hmtl doc') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
          mkdir /Users/laurileskinen/Documents/Programming/adocs_temp
          cp -r /Users/laurileskinen/.jenkins/workspace/Adoc /Users/laurileskinen/Documents/Programming/adocs_temp
        '''
      }
    }
  }
}
