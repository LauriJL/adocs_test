pipeline {
  agent any
  stages {
    stage('Build hmtl doc') {
      agent { dockerfile true }
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
            sh 'p ${JENKINS_HOME}/jobs/workspace/Adoc/ /Users/laurileskinen/Documents/Programming/adocs'
        }
    }
}
