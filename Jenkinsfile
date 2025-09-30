pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo "Building on branch: ${env.BRANCH_NAME}"
                // Simulate a successful build
                sh 'exit 0'
            }
        }
    }
}
