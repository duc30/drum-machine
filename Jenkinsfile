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

        script {
          step ([$class: 'CopyArtifact', projectName: 'drum-machine-pipeline', filter: "public/index.html", target: 'DUCTEST']);
	}
      }
    }
    stage('Deploy') {
      steps {
	sh 'echo Deploy stage'
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
