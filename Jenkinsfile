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
      chmod -R 755 /Users/laurileskinen/Documents/Programming/adocs_temp
      cp -r /Users/laurileskinen/.jenkins/workspace/Adoc/book.html /Users/laurileskinen/Documents/Programming/adocs_temp
      '''
    }
  }
}
