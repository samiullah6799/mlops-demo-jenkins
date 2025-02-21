pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/samiullah6799/mlops-demo-jenkins.git']])
            }
        }

        stage('Building') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Testing') {
            steps {
                sh 'python3 test.py'
            }
        }

        stage('Deployment') {
            steps {
                script {
                    def branchName = ${env.BRANCH_NAME}
                    deploy(branchName)
                }
            }
        }
    }
}

def void deploy(String branchName) {
    if (branchName == 'dev') {
        println(branchName)
    } else {
        println(branchName)
    }
}