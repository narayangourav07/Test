pipeline {
    agent any
    stages {
        stage("Gather Deployment Parameters") {
            steps {
                timeout(time: 30, unit: 'SECONDS') {
                    script {
                        // Show the select input modal
                       def INPUT_PARAMS = input message: 'Please Provide Parameters', ok: 'Next',
                                        parameters: [
                                        choice(name: 'ENVIRONMENT', choices: ['dev','qa'], description: 'Please select the Environment'),
                                        choice(name: 'IMAGE_TAG', choices: ['test', 'test1'], description: 'Available Docker Images'),
                                        string(name: 'node_name', defaultValue: 'test')]
                        env.ENVIRONMENT = INPUT_PARAMS.ENVIRONMENT
                        env.IMAGE_TAG = INPUT_PARAMS.IMAGE_TAG
                        env.nodename = INPUT_PARAMS.node_name
                    }
                }
            }
        }
        stage("Use Deployment Parameters") {
            agent {
                node ("${env.nodename}")
            }
         steps {
                script {
                    echo "All parameters have been set as Environment Variables"
                    echo "node is ${nodename}"
                    echo "Selected Environment: ${env.ENVIRONMENT}"
                    echo "Selected Tag: ${env.IMAGE_TAG}"
                }
         }
        }
    }
}
