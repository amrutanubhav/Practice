pipeline {
    agent any
    environment {
            SSH_CRED = credentials('SSH_CRED')
        }

    stages{
        when { branch pattern: "feature/.*", comparator: "REGEXP" }
        stage('testing on feature branch') {
            
            steps {
                    sh "env"
                    sh "echo test is done on feature branch"

            }
        }

        stage('testing on PR branch') {    
            when { branch pattern: "PR-.*", comparator: "REGEXP" } 
            steps {
                    sh "ansible-playbook robot-testrun.yml -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} -e COMPONENT=mongodb -e ENV=dev"
                    sh "echo test is done on feature branch"

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