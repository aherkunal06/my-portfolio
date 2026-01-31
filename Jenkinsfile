pipeline {
  agent any
  environment {
    DEPLOY_DIR = /usr/share/nginx/html
  }
  stages {
    stage("checkout"){
      steps {
        checkout scm
      }
    }
    stage("deploy to nginx") {
      steps {
        cp -r . $DEPLOY_DIR
        sh '''
        echo "your app is live " 
        sudo systemctl restart nginx
        '''
        
      }
    }
  }
}
