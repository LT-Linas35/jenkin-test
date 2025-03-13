pipeline {
  agent any
  stages {
    stage('Bandymas') {
      when {branch 'main'}
      steps {
        echo "Bandymas main"
        }
      when {branch 'test'}
      steps {
      	echo "Bandymas test"
        }
      }
    }
  }
