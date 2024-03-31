pipeline {
    agent { node { label 'Workstation' } }

    environment {
        TEST_URL = "google.com"
        SSH = credentials("centos-ssh")
    }

    steps {
           //echo 'Hello World'
            //error 'This is an error'
            echo TEST_URL
            echo SSH

            }

          }

        stage('Compile') {
            steps {
                echo 'Compiling code...'
                // Add your compilation steps here
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

        stage('Code Deploy') {
            steps {
                echo 'Deploying code...'
                // Add your code deployment steps here
            }
        }
    }
}
