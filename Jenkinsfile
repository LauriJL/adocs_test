pipeline {
  agent { 
    docker { image 'node:16.13.1-alpine' }
    }
  stages {
    stage('Get version number') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          node --version
        '''
      }
    }
  }
}
