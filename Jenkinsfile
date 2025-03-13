pipeline {
    agent any
    parameter {
        string(name: 'target_env', defaultValue: 'staging', decription: 'Target environment to deploy into(dev,taging,lprod)')
        booloadParam(name: 'run_smoke_tests', defaultValue: true,decription: 'If selected, run smoke tests after deployment')
    }
    stages {
        stage('Deploy') {
            steps {
                echo "Deploying to ${params.target_env} environment..."
            }
        }
        stage('Smoke Test') {
            when {
                expression { params.run_smoke_tests == true }
            }
            steps {
                echo "Running smoke tests..."
            }
        }
    }
}
