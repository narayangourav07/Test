pipeline {
    agent none

    stages {
        stage('checkout') {
            echo "${env.GIT_BRANCH}"
            when {
                // Only say hello if a "greeting" is requested
                expression { env.GIT_BRANCH == 'test' }
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
                expression { env.GIT_BRANCH == 'origin/test' }
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
