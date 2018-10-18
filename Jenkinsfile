pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
	sh 'npm install'
	sh 'npm run build'
	sh 'npm run test'
      }
    }
    stage('Deploy') {
      steps {
      }
    }
    stage('Integration tests') {
      steps {
      }
    }
  }
}
