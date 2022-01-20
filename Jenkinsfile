pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
final scmVars = checkout(scm)
echo "scmVars: ${scmVars}"
echo "scmVars.GIT_COMMIT: ${scmVars.GIT_COMMIT}"
echo "scmVars.GIT_BRANCH: ${scmVars.GIT_BRANCH}"

                echo 'Hello World'
                echo "${env.GIT_BRANCH}"
                println "${env.GIT_BRANCH}"
                
            }
        }
    }
}
