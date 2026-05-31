pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'MAVEN'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'my-private-repo-creds', branch: 'main', url: 'https://github.com/Charandeep2002/Superlab.git'
            }
        }

        stage('Maven Build') {
            steps {
                echo 'Building project'
                sh "${MAVEN_HOME}/bin/mvn clean verify -Dtest=!FormUITest"
            }
        }
    }

    post {
        success {
            echo '✅ Build pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Please check the logs.'
        }
    }
}