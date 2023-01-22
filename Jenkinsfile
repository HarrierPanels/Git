pipeline {
    agent { label 'master2' }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh label: 'Test', script: '''
                    pwd
                    ls -l
		    cp *test /home/a/test
                    cd /home/a/test && ls -l
		    cd $HOME && ls -l
                '''    
            }
        }
    }
}
