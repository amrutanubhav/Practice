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
            when { branch pattern: "PR-.*", comparator: "REGEXP" } 
            steps {
                    sh "ansible-playbook -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} -e COMPONENT=mongodb -e ENV=dev robot-testrun.yml"
                    sh "echo test is done on feature branch"

            }
        }

        // stage('testing on MAin branch') {
        //     steps {
        //         when{
                
        //             branch 'main'

        //         }
        //             sh "env"
        //             sh "echo test  done on feature branch"


        //     }
        // }      
           
    }
}

// test to check 1