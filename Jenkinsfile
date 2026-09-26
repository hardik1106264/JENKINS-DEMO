pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Validate') {
            steps {

                echo 'Checking Student Management Application...'

                sh 'test -f index.html'

                echo 'index.html exists'
            }
        }

        stage('Build') {
            steps {

                echo 'Building application...'

                sh 'mkdir -p build'

                sh 'cp index.html build/index.html'

                echo 'Build completed successfully'
            }
        }

        stage('Test') {
            steps {

                echo 'Running tests...'

                sh 'test -f build/index.html'

                sh 'grep -q "Student Management System" build/index.html'

                echo 'Student application test passed'
            }
        }
    }
}
