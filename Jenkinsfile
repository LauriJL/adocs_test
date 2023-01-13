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
    stage('Push to git'){
      steps{
      sh '''
        git remote add origin git@github.com/LauriJL/adocs_test.git 
        git push -u origin dev
      '''
      }
    }
  }
}
