pipeline {
    agent any

    environment {
        SERVER_LIST_FILE = 'server_list.txt'
    }

    stages {
        stage('Paruošti serverių sąrašą') {
            steps {
                script {
                    def lines = ["pirmas", "antras", "trecias"]
                    writeFile file: SERVER_LIST_FILE, text: lines.join('\n')
                }
            }
        }

        stage('Pasirinkimas') {
            steps {
                script {
                    def serverList = readFile(SERVER_LIST_FILE).split('\n')
                    properties([
                        parameters([
                            choice(name: 'server_list', choices: serverList.join("\n"), description: 'Pasirinkite serverį')
                        ])
                    ])
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to ${params.server_list}"
            }
        }
    }
}
