pipeline {
    agent { label 'master2' }

    stages {
        stage('Start') {
            steps {
                echo '-----START----'
                sh label: 'Test', script: '''
                    pwd
                    ls -l
		    cp *test /home/a/test
                '''    
            }
        }
        stage('Finish') {
            steps {
                echo '-----Finish----'
                sh label: 'Test', script: '''
                    pwd
                    ls -l
                    cd /home/a/test && ls -l
                    cd $HOME && ls -l
                    #cd $JENKINS_HOME && ls -l
                '''    
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
