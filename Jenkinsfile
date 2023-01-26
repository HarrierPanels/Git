pipeline {
    agent { label 'master2' }

    stages {
        stage('Start') {
            steps {
                echo '-----START----'
            }
        }
    }
    post {
        always {
            echo 'Finishing...'
        }
        success {
            echo 'Successful'
        }
        failure {
            echo 'Failed'
        }
        unstable {
            echo 'Unstable'
        }
        changed {
            echo 'The Pipeline has changed'
            echo 'Previously failing but is now successful'
        }
    }
}
