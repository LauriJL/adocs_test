pipeline {
  agent { dockerfile 
         {filename 'Dockerfile'}
        }
  stages {
    stage('Build hmtl doc') {  
      steps {
        echo "Current workspace is $WORKSPACE"
        echo "Build number is ${currentBuild.number}"
        sh '''
          asciidoctor --version
          asciidoctor book.adoc
          mv book.html KeyMobile2_user_manual.html
        '''
      }
    }
    stage('Create artifact of html'){
      steps {
        archiveArtifacts artifacts: '**/*', excludes: '**/Jenkinsfile, **/Dockerfile, **/*.adoc', onlyIfSuccessful: true
        echo "Artifact created"
      }
    }
  }
}
