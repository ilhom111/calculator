pipeline {
    agent {
        label 'generic'
    }
    stages {
        stage("Setup script") {
            steps {
                sh """
                    /usr/bin/pip3.6 install pytest
                """                    
            }//steps
        }//stage
        stage("Run unit tests") {
            steps {
                sh """
                    pytest
                """
            }//steps
        }//stage
    }//stages
    post {
        always {
            sh """
                /usr/bin/pip3.6 uninstall pytest -y
            """
        }//alwasy
    }//post
}//pipeline