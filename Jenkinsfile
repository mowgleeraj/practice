pipeline {
    agent any
    environment {
        name = 'mohan'
    }
    parameters {
        string(name: 'person', defaultValue: 'mohan', description: "who the hell are you")
        booleanParam(name: 'male', defaultValue: true, description: "henge navu")
        choice(name: 'city', choices: ['jaipur','mumbai','dubai'], description: "yen anta hakana")
    }
    stages {
        stage('Run as a command') {
            steps {
                sh '''
                date
                ls
                pwd
                '''
            }
        }
        stage('environment variable') {
             environment {
                username = 'raja'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('parameters') {
            steps {
                 sh 'echo "${person}"'
                 sh 'echo "${username}"'
            }
        }
        stage('continue') {
            input {
                message "is it Likith?"
                ok "yes its Likith"
            }
            steps {
                echo2 'deploy on continue'
            }
        }  
        stage('deploy') {
            steps {
                echo1 'deploy on prod'
            }    
        }        
    }
    post{        
        always{
            echo 'AL'
        }
    }
}
