pipeline {
    agent any

    environment {
        REGION_LIST_FILE = 'regions.txt'
    }

    stages {
        stage('Paruošti regionų sąrašą') {
            steps {
                script {
                    // Gauti AWS regionus iš `curl`
                    def output = sh(script: "curl -s https://raw.githubusercontent.com/aws/aws-sdk-go/main/models/endpoints/endpoints.json | jq -r '.partitions[].regions | keys[]'", returnStdout: true).trim()
                    
                    // Konvertuoti išvestį į sąrašą
                    def server_list = output ? output.split("\n") : []

                    // Įrašyti regionus į failą (naudinga debug'ui)
                    writeFile file: REGION_LIST_FILE, text: server_list.join("\n")

                    // Pakeisti pipeline parametrus su `properties([])`
                    properties([
                        parameters([
                            choice(name: 'server_list', choices: server_list.join("\n"), description: 'Pasirinkite serverį')
                        ])
                    ])
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying to ${params.server_list}"
                }
            }
        }

        stage('Inpect Variables') {
            steps {
                script {
                    sh "printenv"
                }
            }
        }
    }
}
