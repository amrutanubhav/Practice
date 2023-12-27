pipeline {
    agent any
    environment {
            SSH_CRED = credentials('SSH_CRED')
        }

    stages{
        
        stage('testing on feature branch') {
            when { branch pattern: "feature/.*", comparator: "REGEXP" }
            steps {
                    sh "env"
                    sh "echo test is done on feature branch"

            }
        }

        stage('testing on PR branch') {    
            // when { branch pattern: "PR-.*", comparator: "REGEXP" } tets
            steps {
                    sh "ansible-playbook robot-testrun.yml -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} -e COMPONENT=mongodb -e ENV=dev"
                    sh "echo test is done on feature branch"
<<<<<<< HEAD
                    sh "tetsif"
=======
                    sh "testing"
>>>>>>> df8d315da7bd281ec3907b7166b9c87fa7c6da0c

            }
        }

        stage('testing on MAin branch') {
            when{ branch 'main' }
            steps {
                
                    sh "env"
                    sh "echo test  done on feature branch"


            }
        }      
           
    }
}

// test to check 1