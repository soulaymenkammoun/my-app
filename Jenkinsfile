pipeline
{
 agent any
 stages {
 stage('build'){
 steps{
 script{
 sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/hosts.yml"
 }
 }
 
 }
 stage('docker')
 {
 steps{
 script{                
 sh " ansible-playbook  /var/lib/jenkins/workspace/livraison/Ansible/docker.yml -i ansible/hosts.yml "
 }
 }
 }
 stage('Docker login') {

                                         steps {
                                          sh 'echo "login Docker ...."'
                   	sh "docker login -u soulaymendocker123 -p 123456789"
                               }  }
 stage('docker registry')
 {
 steps{
 script{                      
 sh " ansible-playbook  -vvvv /var/lib/jenkins/workspace/livraison/Ansible/docker-registry.yml -i ansible/hosts.yml "
 }
 }
 }
 }
 }
