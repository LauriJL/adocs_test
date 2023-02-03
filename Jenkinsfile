pipeline {
  agent { 
    dockerfile {
      filename 'Dockerfile'
    }
  }
  
  parameters {
    booleanParam(name: 'PROMPT_FOR_HTML, defaultValue: true, description: ‘Create HTML files?’)
  }

  stages {
    stage ('Build hmtl doc') {
      steps {
        script {  
          if (params.PROMPT_FOR_HTML==true) {
            script {
              try {
                timeout(time: 30, unit: 'SECONDS') {
                  input 'Create HTML files?'
                }
                echo "timeout"
              } catch(err) {
                currentBuild.result = 'SUCCESS'
                return
              }
              Echo “with prompt”
              echo "Current workspace is $WORKSPACE"
	            echo "Build number is ${currentBuild.number}"
	            sh '''
	              asciidoctor --version
	              asciidoctor book.adoc
	              mv book.html user_manual.html
	              '''
            }
          } else {
            echo "WITHOUT prompt"
            echo "Current workspace is $WORKSPACE"

            echo "Build number is ${currentBuild.number}"
            sh '''
              asciidoctor --version
              asciidoctor book.adoc
              mv book.html user_manual.html
            '''
            }   
          }
       }
     }

     stage ('Create artifact of html') {
      steps {
        Echo “creating artefact”
        archiveArtifacts artifacts: '**/*', excludes: '**/Jenkinsfile, **/Dockerfile, **/*.adoc, **/*.md', onlyIfSuccessful: true
	      echo "Artifact created"
        }
      }
    }
  }
