pipeline {
    agent any
    options { timestamps() }
    properties([pipelineTriggers([upstream('aws-pipeline-ci3')])])
    stages {
        stage('Non-parallel stage') {
            steps {
                sh 'echo "Checkout..."'
                checkout scm
                //git 'https://github.com/bnm4hi/project_ci1.git'
    
                sh 'echo "Build..."'
                sh 'make'

                sh 'echo "Verify..."'
                sh 'pwd ; ls -al'
            }
        }
    }
}

