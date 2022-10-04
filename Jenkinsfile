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
}
