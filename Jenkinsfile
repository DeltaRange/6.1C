pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven..."
                // Example tool: Maven
                // mvn clean install
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests and integration tests..."
                // Example tools: JUnit for unit testing, Selenium for integration testing
                // mvn test
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Analyzing code quality using SonarQube..."
                // Example tool: SonarQube for code analysis
                // sonar-scanner
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan using OWASP ZAP..."
                // Example tool: OWASP ZAP for security scanning
                // zap-cli quick-scan http://localhost
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to the staging environment..."
                // Example: Deploy to AWS EC2 instance
                // aws deploy create-deployment ...
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment..."
                // Run tests in the staging environment
                // Example: Selenium or JMeter
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to the production environment..."
                // Example: Deploy to AWS EC2 instance
                // aws deploy create-deployment ...
            }
        }
    }

    post {
    success {
        mail to: 'ranul.dewmin@gmail.com',
             subject: "Pipeline Succeeded: ${currentBuild.fullDisplayName}",
             body: "Stage ${env.STAGE_NAME} completed successfully.\n\nView the logs here: ${env.BUILD_URL}"
            }

    failure {
        mail to: 'ranul.dewmin@gmail.com',
             subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
             body: "Stage ${env.STAGE_NAME} failed.\n\nView the logs here: ${env.BUILD_URL}"
            }
        }

}
