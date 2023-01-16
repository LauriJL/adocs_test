pipeline {
  agent { 
    docker { image 'node:16.13.1-alpine' }
    }
  stages {
    stage('Build hmtl doc') {
      steps {
        echo "Current workspace is $WORKSPACE"
        sh '''
          node --version
        '''
      }
    }
  }
}
