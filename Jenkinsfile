pipeline {
  agent { dockerfile true }
  stages {
    stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
    stage('Get version number') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh "asciidoctor --version"
      }
    }
  }
}
