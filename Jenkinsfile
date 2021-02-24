pipeline {
    agent any

    environment {
        NAME = credentials('foo')
    }

    stages {
        stage('Hello') {
            steps {
                sh 'echo "Hello $NAME Demo 1!"'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
