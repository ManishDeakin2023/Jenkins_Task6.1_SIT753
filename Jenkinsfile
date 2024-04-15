pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Use Maven to build the project
                sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Use JUnit for unit tests and JUnit + Mockito for integration tests
                sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                // Use SonarQube for code analysis
                sh 'mvn sonar:sonar'
            }
        }
        stage('Security Scan') {
            steps {
                // Use OWASP Dependency-Check for vulnerability scanning
                sh 'dependency-check.sh --project MyProject --scan ./'
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Use AWS CLI to deploy to an EC2 instance
                sh 'aws ec2 run-instances --image-id ami-abc12345 --count 1 --instance-type t2.micro'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Use Postman/newman for API testing
                sh 'newman run mycollection.json'
            }
        }
        stage('Deploy to Production') {
            steps {
                // Use AWS CLI to deploy to an EC2 instance
                sh 'aws ec2 run-instances --image-id ami-abc12345 --count 1 --instance-type t2.micro'
            }
        }
    }
    post {
        success {
            mail to: 'mail2manish599@gmail.com',
                 subject: "Job '${env.JOB_NAME} ${env.BUILD_NUMBER}'",
                 body: "Job '${env.JOB_NAME} ${env.BUILD_NUMBER}' finished. Result: ${currentBuild.result}"
        }
    }
}
