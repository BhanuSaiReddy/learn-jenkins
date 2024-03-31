pipeline {
    agent { node { label 'Workstation' } }

    environment {
        TEST_URL = "google.com"
        SSH = credentials("centos-ssh")
    }

    options {
        ansiColor('xterm')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    triggers { pollSCM('*/1 * * * *') }

    stages {
        stage('Preparation') {
            steps {
                script {
                    echo TEST_URL
                    echo SSH
                    sh 'env'
                    sh "ansible -i 172.31.27.197, all -e ansible_user=${env.SSH_USR} -e ansible_password=${env.SSH_PSW} -m ping"
                }
            }
        }

        stage('Compile') {
            steps {
                input {
                    message "Should we continue?"
                    ok "Yes, we should."
                }
                // Add compilation steps here
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

