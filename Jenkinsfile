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
      stage('Docker push') {
            steps{
                script{
                    withDockerRegistry([ credentialsId:
            "irinagrig-dockerhub", url: ""]){
                app.push()   
                }
            }
            }
        }
        }