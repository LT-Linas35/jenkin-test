def getServerList() {
    def serverListFile = new File('server_list.txt')
    if (serverListFile.exists()) {
        return serverListFile.readLines()
    } else {
        return ["pirmas", "antras", "trecias"]
    }
}

pipeline {
    agent any

    stages {
        stage('Example') {
            steps {
                script {
                    def lines = ["pirmas", "antras", "trecias"]
                    writeFile file: 'server_list.txt', text: lines.join('\n')
                    echo "IIIIIIIIIIIIIIIIIIII"
                }
            }
        }
    
    }
}