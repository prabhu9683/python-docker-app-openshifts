node{
   
   stage(" Code Checkout"){
      echo 'App build started..'
      git credentialsId: 'GitHubID', url':https://github.com/prabhu9683/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "prabhu9683-py-app"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag prabhu9683-py-app  prabhu9683-py-app:dev'
          sh 'docker push prabhu9683-py-app:dev'
          sh 'docker push prabhu9683-py-app:latest'
      }
    }
    stage("App deployment started"){
     //sh 'oc login --token=t01XSPheqChA1n1QxmPCSJAwm5rFNYzb7FvRP9mmg6A --server=https://api.us-east-1.online-starter.openshift.com:6443'
          // sh 'oc new-project creativetech'
      
    // sh 'oc new-app shiddu/pythonimage:dev --name python --env NEWRELIC_LICENSE=xxxxxx NEWRELIC_APPNAME=pyapp'
    // sh 'oc expose svc python --name=python'
    // sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   


   
























}
