pipeline {
    agent any

parameters {
    choice(name: 'server_list', choices: getServerList(), description: 'Environment to deploy')
}

def getServerList() {
    def server_list = new File('server_list.txt')
    return server_list.readLines()
    }

stages {
    stage() {
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