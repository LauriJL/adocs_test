pipeline {
  agent { dockerfile true }
  stages {
    stage('Build hmtl doc') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
          USER root
          mkdir -p /Users/laurileskinen/Documents/Programming/adocs_temp
          USER jenkins
          cp -r /Users/laurileskinen/.jenkins/workspace/Adoc ./Users/laurileskinen/Documents/Programming/adocs_temp
        '''
      }
    }
  }
}
