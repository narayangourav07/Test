pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                def getGitBranchName() {
                return scm.branches[0].name
                }

                echo 'Hello World'
                echo "${env.GIT_BRANCH}"
                sh 'printenv'
                
            }
        }
    }
}
