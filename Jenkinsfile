pipeline {
    agent any
    options { 
	    timestamps()
	    //pipelineTriggers([upstream('aws-pipeline-ci3')]) 
    }
    //options([pipelineTriggers([upstream('aws-pipeline-ci3')])])
    stages {
        stage('Non-parallel stage') {
            steps {
		// build ci3
                build job : 'aws-pipeline-ci3'

		// if clause for ci1 if ci3 was successful
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

