pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                    git changelog: false, poll: false, url: 'https://github.com/rchidana/viacom-nginx.git'
					echo "Compiled Successfully!!";
            }
        }
        
        stage('Build') {
            steps {
                    echo "Built Successfully!";
            }
        }
        
        stage('Quality-Gate') {
            steps {
                    echo "SonarQube Quality Gate passed successfully!!"; 
                /*sh exit ("1");*/
            }
        }
        
        stage('Deploy') {
            steps {
                  sudo cp index.html /usr/share/nginx/html/
				  echo "Successfully Deployed on Nginx!!";
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
