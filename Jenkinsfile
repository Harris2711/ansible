pipeline {
    agent any
    stages {
        stage('SCM checkout') {
            steps{
                git branch: 'main', url: 'https://github.com/Harris2711/ansible.git'
            }
        }
        stage('execute ansible') {
            steps {
                ansiblePlaybook credentialsId: 'ansible', installation: 'ansible2', inventory: 'web.inv', playbook: 'ansible.yml'
            }
        }
        stage('email'){
            steps{
                emailext attachLog: true, body: 'this is pipeline sucess email', subject: 'this is pipeline sucess email', to: 'mohammedharris556@gmail.com'
            }
        }
    }
}
