pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo "🛠️ Cloning Private Gitub repository"
                git credentialsId: 'my-private-repo-creds', branch:'main', url:'https://github.com/Charandeep2002/Superlab.git'
            }
        }

        stage('Stage 2 - Name Here') {
            steps {
                echo "🔍 Step description here"
                // Commands here
            }
        }

        // ➕ Add more stages as needed
    }

    post {
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed. Please check the logs."
        }
    }
}