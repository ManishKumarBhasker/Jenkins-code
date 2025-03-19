pipeline {
    agent any
      environment {
          name = 'Manish'
      }
      parameters{
          string(name: 'person', defaultValue: 'Isha Manish', description: "who are you?")
          booleanParam(name: 'IsMale', defaultValue: 'true', description: "")
      }
    stages {
        stage('Run a command') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
            }
        }
        stage('Environment veriable') {
             environment {
          username = 'Manish'
      }
            steps {
               sh 'echo "${BUILD_ID}"'
             
               sh 'echo "${name}"'
               sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                sh 'echo "${BUILD_ID}"'
             
               sh 'echo "${name}"'
               sh 'echo "${person}"'
            }
        }
        stage('Continue ?') {
            input{
                message "should we continue?"
                ok "Yes we should"
            }
            steps {
                echo 'Deploy on prod'
            }
        }
        stage('Deploy on Prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
    
        post {
            always{
                echo 'I will always say hello again'
            }
            failure{
                echo 'Failure'
            }
            success{
                echo 'Success'
            }
        }
    }

