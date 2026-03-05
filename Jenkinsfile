pipeline {
 agent any

 stages {

  stage('Clone') {
   steps {
    git 'https://github.com/yourusername/devops-cicd-project.git'
   }
  }

  stage('Build Docker Image') {
   steps {
    sh 'docker build -t yourdockerhubusername/devops-app .'
   }
  }

  stage('Push Docker Image') {
   steps {
    sh 'docker push yourdockerhubusername/devops-app'
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
