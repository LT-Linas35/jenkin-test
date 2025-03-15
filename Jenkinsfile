def getServerList() {
    def server_list = new File('server_list.txt')
    return server_list.readLines()
}

def iasyti() {
    def lines = ["pirmas", "antras", "trecias"]
        writeFile file: 'server_list.txt', text: lines.join('\n')
}

iasyti()

pipeline {
    agent any

    parameters {
        choice(name: 'server_list', choices: getServerList(), description: 'Environment to deploy')
    }
}