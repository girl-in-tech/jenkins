node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Docker build') {
            steps{
                script{
                     dockerImage = docker.build("magdalenam/frontend")         
                }
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
}

