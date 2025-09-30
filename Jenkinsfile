pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building application for branch: ${env.BRANCH_NAME}"
                sh 'npm install' // Example build step
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'npm test' // Run all tests by default
            }
        }

        stage('Deployment') {
            when {
                // Only run this stage if the branch is 'main' or 'develop'
                expression { return env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'develop' }
            }
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        echo "Deploying to PRODUCTION environment!"
                        // sh './deploy-prod.sh'
                    } else if (env.BRANCH_NAME == 'develop') {
                        echo "Deploying to STAGING/QA environment."
                        // sh './deploy-staging.sh'
                    }
                }
            }
        }
    }
}
