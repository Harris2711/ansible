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
                ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'ansible', inventory: 'web.inv', playbook: 'ansible.yml'
            }
    }
}
