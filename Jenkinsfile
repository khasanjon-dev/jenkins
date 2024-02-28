pipeline {
    agent any
    stages {

        stage ('checkout') {
                steps {
                checkout scmGit(branches: [[name: 'dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/khasanjon-dev/jenkins.git']])
                }
        }

        stage ('install need packages') {
                steps {
                sh 'python3 -m pip install -r requirements.txt'
                }
        }

        stage ('Test'){
                steps {
                sh "python3 test_calculate.py"
                }
        }
      }
    }