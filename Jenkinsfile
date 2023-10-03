pipeline {
    agent any
    stages {
        stage ('pull code') {
            steps {
                sh 'echo "code pulled suceessfully"'
                git credentialsId: 'ssh-key-cred', url: 'git@github.com:Devops-b1/students.git'
            }
        }
        stage ('build stage') {
            steps {
                echo "bulid artifact succesfully"
            }
        }
        stage ('test stage') {
            steps {
                echo "report save successfully"
            }
        }
        stage ('deploy stage') {
            steps {
                echo "app depoly successfully"
            }
        }

    }
}
