pipeline {
    agent any

parameters {
    string(name: 'artifact_version', defaultValue: '1', description: 'set artifact version')
}

stages {
    stage('Deploy') {
        steps {
            echo "Deploying artifact version ${params.artifact_version}"
        }
    }
}

}