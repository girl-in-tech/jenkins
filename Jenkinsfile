node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            app = docker.build("magdalenam/test")    
       }     
      stage('Test image') {           
            app.inside {            
             
             sh 'echo "Tests passed"'        
            }    
        }     
       stage('Push image') {
             steps{
                script{
                    withDockerRegistry([ credentialsId:
            "docker-id", url: ""]){
                dockerImage.push()   
                }
            }
            }
        }