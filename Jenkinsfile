pipeline {
    agent build_server
     
    stages {       
          stage('Ansible Init') {
            steps {
                script {
                
               def tfHome = tool name: 'Ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
        
        
        
        stage('Ansible Deploy') {
             
            steps {
                 
             
               
               sh "ansible-playbook main.yml -i inventories/dev/hosts --user Muralidhar -e '@configs/dev.yml'"

               
            
            }
        }
    }
}
