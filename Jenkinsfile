pipeline {
    agent any
    environment{
        MAVEN_HOME = tool 'MAVEN' 
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo "🛠️ Cloning Private Gitub repository"
                git credentialsId: 'my-private-repo-creds', branch:'main', url:'https://github.com/Charandeep2002/Superlab.git'
            }
        }
        stage('Check Java') {
           steps {
               sh 'java -version'
               sh 'javac -version'
               sh 'mvn -version'
               sh 'echo $JAVA_HOME'
               sh 'ls -l /usr/lib/jvm'
           }
        }
        stage('Maven Build') {
            steps {
                echo "Building Project"
                sh "${MAVEN_HOME}/bin/mvn clean verify -Dtest=!FormUItest"
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