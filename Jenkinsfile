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
                emailext body: '''please check ${BUILD_URL}
"Jenkins Build Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}"''', subject: 'Dear team pipeline is ${currentBuild.result}', to: 'mohammedharris556@gmail.com'
            }
        }
    }
}
