pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo "${env.GIT_BRANCH}"
            }
        }
    }
}
