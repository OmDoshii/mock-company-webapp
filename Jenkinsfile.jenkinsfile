pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // TODO: Add the build step here
                sh './gradlew assemble'
            }
        }
        
        stage('Test') {
            steps {
                // TODO: Add the test step here
                sh './gradlew test'
            }
        }
    }
    
    post {
        always {
            junit '**/build/test-results/**/*.xml'
            archiveArtifacts artifacts: 'build/libs/**/*.jar', allowEmptyArchive: true
        }
    }
}
