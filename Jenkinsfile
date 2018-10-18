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
      }
    }
    stage('Integration tests') {
      steps {
	sh 'echo Integration tests stage'
      }
    }
  }
}
