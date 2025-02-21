pipeline {
    agent any
    stages {
        stage{
            steps('Checkout') {
                checkout scmGit(branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/samiullah6799/mlops-demo-jenkins.git']])
            }
        }

        stage{
            steps('Building') {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage {
            steps ('Testing') {
                sh 'pytest test.py'
            }
        }

        stage {
            steps ('Deployment') {
                echo "Deployment"
            }
        }
    }
}