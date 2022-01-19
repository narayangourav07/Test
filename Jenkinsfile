pipeline {
    agent none

    stages {
        stage('checkout') {
            when {
                // Only say hello if a "greeting" is requested
                expression { env.GIT_BRANCH == 'origin/master' }
            }
            agent {
               node {
                label 'testing-server'
                customWorkspace '/home/ubuntu/LC-WP'
                 }
            }
            steps {
                checkout scm
            }
        }
        stage('Hello') {
            when {
                // Only say hello if a "greeting" is requested
                expression { env.GIT_BRANCH == 'origin/master' }
            }
            agent {
               node {
                label 'testing-server'
                customWorkspace '/home/ubuntu/LC-WP'
                 }
            }
            steps {
                echo 'Hello World'
                echo "${env.GIT_BRANCH}"
            }
        }
    }
}
