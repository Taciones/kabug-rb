pipeline{
    agent {
        docker {
            image 'ruby'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Building or Resolve depencendies!'
                sh 'bundle install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running regression tests.'
            }
        }
        stage('UAT') {
            steps {
                echo 'Wait for User Acceptance.'
                input(message: 'Go to production?', ok: 'Yes')
            }
        }
        stage('PROD') {
            steps {
                echo 'WebApps ready for PROD'
            }
        }
    }
}
