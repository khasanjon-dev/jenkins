pipeline {
    agent any
    stages {

        stage ('checkout') {
                steps {
                checkout scmGit(branches: [[name: 'dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/khasanjon-dev/jenkins.git']])
                }
        }
        stage ('create environment') {
                steps {
                sh 'python3 -m venv venv'
                }
        }
        stage ('environment activate') {
                steps {
                sh '. venv/bin/activate'
                }
        }
        stage ('install packages') {
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