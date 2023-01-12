pipeline {

agent any
	
  stages {
    stage("Build") {
      steps {
        echo 'building the application'
      }
    }
    stage("Testing docker") {
	agent { label 'docker' }
      	steps {
		script {
			docker.image('asciidoctor/docker-asciidoctor' ).inside('-v /root/.m2:/root/.m2') {
              		sh('asciidoctor --help')
	      		}
        	echo 'testing docker image'
	}
    }
  }
}
}
