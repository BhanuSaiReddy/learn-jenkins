pipeline {
    agent { node { label 'Workstation' } }

    environment {
        TEST_URL = "google.com"
        SSH = credentials("centos-ssh")
    }

    options {
      ansiColor('xterm')
      }

    stages {
        stage('Preparation') {
            steps {
                script {
                    echo TEST_URL
                    echo SSH
                    sh 'env'
                    sh 'ansible -i 172.31.27.197, all -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -m ping'
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                // Add your build steps here
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your testing steps here
            }
        }

        stage('Code Quality') {
            steps {
                echo 'Checking code quality...'
                // Add your code quality checking steps here
            }
        }

        stage('Code Secure') {
            steps {
                echo 'Checking code security...'
                // Add your code security checking steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying code...'
                // Add your code deployment steps here
            }
        }
    }
}
