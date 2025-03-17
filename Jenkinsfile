pipeline {
    agent any
    stages {
        stage('Build Backend') {
            steps {
                dir('backend') {
                    script {
                        sh 'echo mvn run build'
                    }
                }
            }
        }
        stage('Build Frontend') {
            steps {
                dir('frontend') {
                    script {
                        sh 'echo npm install'
                        sh 'echo npm run build'
                    }
                }
            }
        }
        parallel {
            stage('Test Backend') {
                steps {
                    dir('backend') {
                        load Jenkinsfile
                    }
                }
            }
            stage('Test Frontend') {
                steps {
                    dir('frontend') {
                        load Jenkinsfile
                    }
                }
            }
        }
    }
}