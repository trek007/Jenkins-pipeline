pipeline {
    agent any
    environment {
        name = 'Vishwajeet'
    }
    parameters {
        string(name: 'person', defaultValue: '', description: "Who are you?") 
    }

    stages {
        stage('Command') {
            steps {
                sh '''
                date
                ls
                pwd
                cal 2023
                '''
            }
        }
        stage('Environment Variable') {
            environment {
                Username = 'Saurav'
            }
            steps {
                sh 'echo "${name}"'
                sh 'echo "${Username}"'
            }
        }
         stage('Parameter') {
            steps {
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message ("Should we continue ?")
                ok ("Yes, we should.")
            }
            steps {
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
         stage('Deploy on Prod') {
            steps {
                sh 'echo "${name}"'
                sh 'echo "${person}"' 
             }
         }
    }
    post {
        always {
            echo "I will always say hello"
            }
        failure {
            echo "Failed"
        }
        success {
            echo "Success"
        }
    }
}
