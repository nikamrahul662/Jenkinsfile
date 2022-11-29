pipeline {
    agent any
    environment {
        name = 'admin'
    }
    parameters {
        string(name: 'Person', defaultValue: 'Ranbir', description: "who are you")
    }

    stages {
        stage('Run a Command') {
            steps {
               sh '''
               date
               ls
               pwd
               '''
            }
        }
        stage('Environment Variables') {
            steps {
                sh 'echo "$(BUILD_ID)"'
                sh 'echo "$(name)"'
            }
        }
        stage('Parameters') {
            steps {
                sh 'echo "$(Person)"'
            }
        }
        stage('echo line') {
            steps {
               echo 'firt step'
            }
        }
        stage('run command') {
            steps {
               sh 'pwd'
            }
        }
        stage('Continue ?') {
            input {
                message "should we continue"
                ok "yes, we should"
                
            }
            steps {
                echo 'Hello DeployOnprod'
            }
        }
        stage('deploy prod') {
            steps {
                echo "hi"
            }
        }
    }
    post {
    always {
        echo "I will always says hello"
    }
    failure {
        echo "failure"
    }
    success {
        echo "success"
    }
    }
    
}
