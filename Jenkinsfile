pipeline {
  agent any
  environment {
    DEPLOY_DIR = "/usr/share/nginx/html"
  }
  stages {
    stage("checkout"){
      steps {
        checkout scm
      }
    }
    stage("deploy to nginx") {
      steps {
        sh '''
        cp -r . $DEPLOY_DIR
        echo "your app is live " 
        sudo systemctl restart nginx
        '''
        
      }
    }
  }
}
