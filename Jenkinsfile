pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/udit1911/Oriserve_assignment.git'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    def remote = [:]
                    remote.name = 'EC2 Server'
                    remote.host = '35.154.171.195'
                    remote.user = 'ec2-user'
                    remote.identityFile = '/home/udit/Downloads/oriservessh.pem'
                    remote.allowAnyHosts = true

                    sshPut remote: remote, from: 'index.html', into: '/var/www/html/'
                }
            }
        }
    }
}
