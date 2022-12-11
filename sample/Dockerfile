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
                    sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.95.136'
                    sh 'scp /var/lib/jenkins/workspace/pipeline/project/* ec2-user@172.31.95.136:/home/ec2-user'
                }
            }
        }
          stage('docker build image') {
            steps { 
                sshagent(['ansible']) {
                    sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.95.136 cd /home/ec2-user/'
                    sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.95.136 docker image build -t $JOB_NAME:V1.$BUILD_ID .'
                    sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.95.136 docker image tag $JOB_NAME:V1.$BUILD_ID rakesh914327/$JOB_NAME:latest'
                }
            }
        }
    }
}