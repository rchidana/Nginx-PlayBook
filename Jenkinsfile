pipeline {
    agent any
    stages {
        stage('check-out') {
            steps {
                    echo "Checking out the Playbook!!";
                    git changelog: false, poll: false, url: 'https://github.com/rchidana/Nginx-PlayBook.git'
                    
            }
        }
        
        stage('Running Playboook') {
            steps {
                    echo "Running NGINX Playbook!";
                    ansiblePlaybook 'nginx_playbook.yml'
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
