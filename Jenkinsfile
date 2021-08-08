node {
     def app 
     stage('clone repository') {
      checkout scm  
    }
     stage('Build docker Image'){
      app = docker.build("devopslakwal/deepak")
    }
     stage('Test Image'){
       app.inside {
         sh 'echo "TEST PASSED"' 
      }  
    }
     
     stage('Push Image'){
       docker.withRegistry('https://registry.hub.docker.com', 'docker_id') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")   
   }
}
}
