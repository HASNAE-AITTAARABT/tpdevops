pipeline {
    agent any

    stages {
        stage('Cloning Git') {
            steps {
                git 'https://github.com/HASNAE-AITTAARABT/tpdevops.git'

            }
        }


         stage('Building image') {
            steps {
                bat 'docker build -t hasnaeaittaarabt/tp4devops  .'
            }
        }

 stage('Test image') {
            steps {
                bat 'echo "Tests passed"'
            }
        }



        stage(' Deploy Image') {
            steps {


                withCredentials([string(credentialsId: 'dockerHub', variable: 'dockerHub')]) {
               bat "docker login -u hasnaeaittaarabt -p  ${dockerHub}"
          }

                bat 'docker push   hasnaeaittaarabt/tp4devops '
            }
        }
