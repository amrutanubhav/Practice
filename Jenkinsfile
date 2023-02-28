pipeline {
    agent any
    environment {
            SSH_CRED = credentials('SSH_CRED')
        }

    stages{
        stage('testing on feature branch') {
            steps {
                when{
                
                    branch pattern: "feature-.*", comparator: "REGEXP"

                }
                    sh "env"
                    sh "echo test is done on feature branch"


            }
        }

        stage('testing on PR branch') {     
            steps {
                when{
                
                    branch pattern: "PR-.*", comparator: "REGEXP"  

                }
                    sh "ansible-playbook -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} -e COMPONENT=Mongodb -e ENV=dev robot-testrun.yml"
                    sh "echo test is done on feature branch"


            }
        }
<<<<<<< HEAD
        stage('testing on MAIN branch') {
=======
        stage('testing on MAin branch') {
>>>>>>> 59e65779cc6d21ce9f760f5a5be9d1b320c0d405
            steps {
                when{
                
                    branch 'main'

                }
                    sh "env"
                    sh "echo test  done on feature branch"


            }
        }      
           
    }
}

// test to check 