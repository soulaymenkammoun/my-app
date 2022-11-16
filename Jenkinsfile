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
 sh " ansible-playbook Ansible/docker.yml -i Ansible/inventory/hosts.yml -e ansible_become_password=root"
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
 sh " ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/hosts.yml -e ansible_become_password=root "
 }
 }
 }
 }
 }
