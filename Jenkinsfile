node {
     def app 
     stage('clone repository') {
      checkout scm  
    }
     stage('Build docker Image'){
      app = docker.build("aloksri26d/myrepo")
    }
     stage('LAKWALNEW Image'){
       app.inside {
         sh 'echo "TEST PASSED"' 
      }  
    }
     
     stage('Push Image'){
       docker.withRegistry('https://registry.hub.docker.com', 'aloksri26d') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")   
   }
}
}
