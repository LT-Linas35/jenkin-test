pipeline {
    agent any
    parameters {
        string(name: 'target_env', defaultValue: 'staging', description: 'Target environment to deploy into (dev, staging, prod)')
        booleanParam(name: 'run_smoke_tests', defaultValue: true, description: 'If selected, run smoke tests after deployment')
    }
    stages {
        stage('Deploy to dev') {
            when {
                expression { params.target_env != 'dev' }
            }
            steps {
                echo "Deploying to ${params.target_env} environment..."
            }
        }
        stage('Deploy to staging') {
            when {
                expression { params.target_env != 'staging' }
            }
            steps {
                echo "Deploying to ${params.target_env} environment..."
            }
        }
        stage('Deploy to prod') {
            when {
                expression { params.target_env != 'prod' }
            }
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
