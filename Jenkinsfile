pipeline {
  agent any
  stages {
    stage('Bandymas main') {
      when {branch 'main'} steps { echo "Bandymas main" }
    stage('Bandymas test') { 
      when {branch 'test'} steps { echo "Bandymas test" }
    }
   }
 }
