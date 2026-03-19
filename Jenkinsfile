pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/OmkarParab2001/devops-project.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t devops-app .'
      }
    }

    stage('Stop Old Container') {
      steps {
        sh 'docker rm -f devops-container || true'
      }
    }

    stage('Run New Container') {
      steps {
        sh 'docker run -d -p 3000:3000 --name devops-container devops-app'
      }
    }
  }
}
