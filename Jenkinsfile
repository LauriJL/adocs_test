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
    stage('Create artifact of html'){
      steps {
        archiveArtifacts artifacts: '**/*.html', onlyIfSuccessful: true
        echo "Artifact created"
      }
    }
  }
  post {
       always {
        echo 'I will always say Hello again!'
        sh '''
        cp /Users/laurileskinen/.jenkins/workspace/Adoc/book.html /Users/laurileskinen/Documents/Programming/adocs
         '''
        }
    }
}
