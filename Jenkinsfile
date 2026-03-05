pipeline {
 agent any

 stages {

  stage('Clone') {
    steps {
        git branch: 'main', url: 'https://github.com/DollySingarapu/devops-cicid-project.git'
    }
}
  }

  stage('Build Docker Image') {
   steps {
    sh 'docker build -t dollysingarapu/devops-app .'
   }
  }

  stage('Push Docker Image') {
   steps {
    sh 'docker push dollysingarapu/devops-app'
   }
  }

  stage('Deploy to Kubernetes') {
   steps {
    sh 'kubectl apply -f deployment.yaml'
    sh 'kubectl apply -f service.yaml'
   }
  }

 }

}
