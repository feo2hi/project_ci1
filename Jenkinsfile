pipeline {
    agent any
    options { 
	    timestamps()
	    //pipelineTriggers([upstream('aws-pipeline-ci3')]) 
    }
    stages {
        stage('build ci1') {
            steps {
                build(job : 'aws-pipeline-ci3')
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

