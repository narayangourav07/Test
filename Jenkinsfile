pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                def branchName = getCurrentBranch()
                echo 'My branch is' + branchName

                def getCurrentBranch () {
                  return sh (
               script: 'git rev-parse --abbrev-ref HEAD',
                returnStdout: true
                 ).trim()
                }
                echo 'Hello World'
                echo "${env.GIT_BRANCH}"
                println "${env.GIT_BRANCH}"
                
            }
        }
    }
}
