pipeline {

  agent any

  stages {
	stage ('Build - AsciiDoc Document') {
      steps {
          script {
            docker.image('maven:3.6-jdk-12').inside('-v /root/.m2:/root/.m2') {
              sh('mvn -B generate-resources') // AsciiDoc Target PDF
            }
          }
          archiveArtifacts 'pdf/asciidoc.pdf' // Put the artefact to the build artefacts.
      }
    }
  }
  post {
    always {
      echo 'One way or another, I have finished'
    }
    success {
      echo 'I succeeeded!'
    }
    unstable {
      echo 'I am unstable :/'
    }
	  failure {
      echo 'Failure: Check Error Log'
    }
		cleanup {
			cleanWs() // Delete the whole Workspace
		}
  }
}
