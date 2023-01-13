pipeline {
  agent { dockerfile true }
  stages {
    stage('Build hmtl doc') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
        '''
      }
    }
  }
  post {
    always {
      echo "Post OK!"
      sh '''
      COPY /Users/laurileskinen/.jenkins/workspace/Adoc /A /Users/laurileskinen/Documents/Programming/adocs_temp /A
      '''
    }
  }
}
