pipeline {
    agent any

    stages {
        stage('vcs') {
            steps {
                git 'https://github.com/rakesh914327/docker.git'
            }
        }
        stage('sending dockerfile ansible server over ssh') {
            steps { 
                sshagent(['ansible']) {
                sh 'ssh -o StrictHostKeyChecking=no ec2-user@3.86.114.96'
                sh 'scp /var/lib/jenkins/workspace/pipeline/project/* ec2-user@3.86.114.96:/home/ec2-user'
                }
            }
        }
    }
}