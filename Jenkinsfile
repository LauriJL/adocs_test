pipeline {

agent any
	
  stages {
    stage("Build") {
      steps {
        echo 'building the application'
      }
    }
    stage("Testing docker") {
      steps {
	agent {
    		docker { image 'asciidoctor/docker-asciidoctor' }
  		}
	script {
		docker.inside('-v /root/.m2:/root/.m2') {
              		sh('asciidoctor --help')
	      	}
        echo 'testing docker image'
	}
    }
  }
}
}
