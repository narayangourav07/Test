pipeline {
    agent none

    stages {
        stage('test') {
            steps{
                  echo "${env.GIT_BRANCH}"
            }
        }
        stage('checkout') {
            when {
                // Only say hello if a "greeting" is requested
                expression { env.GIT_BRANCH == 'main' }
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
                expression { env.GIT_BRANCH == 'origin/main' }
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
