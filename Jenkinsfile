pipeline {
  agent any
  environment {
    MONGO_URI = credentials('mongo-uri') // Setup this secret in Jenkins credentials
  }
  triggers {
    scm('* * * * *') // or use GitHub webhook
  }
  stages {
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Build & Deploy') {
      steps {
        sh 'node server.js'
      }
    }
  }
}
