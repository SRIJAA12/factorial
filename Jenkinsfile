pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java Program'

                sh '''
                    mkdir -p build
                    javac -d build src/Main.java
                '''
            }
        }

        stage('Execute') {
            steps {
                echo 'Executing Factorial Program'

                sh '''
                    echo "5" | java -cp build Main
                '''
            }
        }
    }
}