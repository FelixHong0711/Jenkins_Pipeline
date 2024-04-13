// add comment
pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo 'Building the code using Maven...'
            }
        }
        stage('Unit and Integration Tests'){
            steps{
                echo 'Running unit tests using JUnit...'
                echo 'Running integration tests using Selenium...'
            }
            post{
                success{
                    emailext(to: 'felixhong0720@gmail.com',
                    subject: 'Unit and Integration Tests Status Email',
                    body: 'The tests are successful',
                    attachLog: true)
                }
                failure{
                    emailext(to: 'felixhong0720@gmail.com',
                    subject: 'Unit and Integration Tests Status Email',
                    body: 'The tests are failed',
                    attachLog: true)
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo 'Running code analysis using SonarQube...'
            }
        }
        stage('Security Scan'){
            steps{
                echo 'Performing security scan using OWASP ZAP...'
            }
            post{
                success{
                    emailext(to: 'felixhong0720@gmail.com',
                    subject: 'Security Scan Status Email',
                    body: 'The security scan is successful',
                    attachLog: true)
                }
                failure{
                    emailext(to: 'felixhong0720@gmail.com',
                    subject: 'Security Scan Status Email',
                    body: 'The security scan is failed',
                    attachLog: true)
                }
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo 'Deploying the application to AWS EC2 instance using AWS CodeDeploy...'
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo 'Running integration tests on staging environment using Selenium...'
            }
        }
        stage('Deploy to Production'){
            steps{
                echo 'Deploying the application to AWS EC2 instance using AWS CodeDeploy...'
            }
        }
    }
}
