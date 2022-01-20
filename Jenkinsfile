pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo "${env.GIT_BRANCH}"
                sh 'printenv'
                
            }
        }
    }
}
