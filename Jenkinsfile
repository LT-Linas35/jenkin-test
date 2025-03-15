pipeline {
    agent any

parameters {
    choice(name: 'ENV', choices: ['DEV', 'QA', 'PROD'], description: 'Environment to deploy')
}

stages {
    stage('Environment') {
        steps {
            script {
                if (params.ENV == 'DEV') {
                    echo 'Deploying to DEV'
                } else if (params.ENV == 'QA') {
                    echo 'Deploying to QA'
                } else if (params.ENV == 'PROD') {
                    echo 'Deploying to PROD'
                }
            }
        }
    }
}

}