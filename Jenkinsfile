pipeline {
    agent any
    parameters {
        string(name: 'target_env', defaultValue: 'staging', description: 'Target environment to deploy into (dev, staging, lprod)')
        booleanParam(name: 'run_smoke_tests', defaultValue: true, description: 'If selected, run smoke tests after deployment')
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
