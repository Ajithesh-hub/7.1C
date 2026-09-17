pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Task: Compile and bundle application source into a deployable build artifact.'
                echo 'Tool: Webpack (with Babel for transpilation)'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Task: Run unit tests on individual modules and integration tests to verify components work together.'
                echo 'Tool: Mocha + Chai (unit), Supertest (API integration)'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Task: Analyse the codebase for style violations, anti-patterns and maintainability issues.'
                echo 'Tool: ESLint (Airbnb style guide)'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Task: Scan source code, dependencies and config for known vulnerabilities and exposed secrets.'
                echo 'Tool: Trivy (filesystem / dependency / secret scan)'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Task: Deploy the build artifact to a staging server mirroring production.'
                echo 'Tool: AWS CodeDeploy to an AWS EC2 staging instance (PM2 process manager)'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Task: Run integration tests against the live staging environment.'
                echo 'Tool: Postman/Newman automated API regression suite'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Task: Promote the verified build to the production server.'
                echo 'Tool: AWS CodeDeploy to AWS EC2 production instance (rolling/blue-green deployment)'
            }
        }
    }
}
