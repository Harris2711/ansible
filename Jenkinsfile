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
                emailext body: '"Dear team pipeline is ${currentBuild.result} please check ${BUILD_URL} or PFA build log", compressLog: false,', 
                subject: 'Jenkins build notification: $PROJECT_NAME - Build # $BUILD_NUMBER - $BUILD_STATUS', to: 'mohammedharris556@gmail.com'
            }
        }
    }
}
