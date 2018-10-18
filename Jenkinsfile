pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
	wrap([$class: 'AnsiColorBuildWrapper', 'colorMapName': 'xterm']) {
	  sh 'echo Build stage'
	  sh 'npm install'
	  sh 'npm run build'
	  sh 'npm run test'
	}
      }
    }
    stage('Deploy') {
      steps {
	sh 'echo Deploy stage'

        script {
          step ([$class: 'CopyArtifact', projectName: 'drum-machine-pipeline', filter: "public/**", target: 'DUCTEST']);
        }
      }
    }
    stage('Integration tests') {
      steps {
	sh 'echo Integration tests stage'
	sh 'curl -i http://localhost:8081'
      }
    }
  }
}
