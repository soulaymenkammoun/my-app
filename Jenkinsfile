pipeline{
    agent any
    stages{
       stage('GetCode'){
            steps{
                git branch: 'master',
                url : 'https://github.com/soulaymenkammoun/my-app.git'
            }
       }
       stage('build'){
            steps{
                script{
                  sh " ansible-playbook ansible/build.yml -i ansible/hosts.yml "
             }
          }
        }
    }
}
