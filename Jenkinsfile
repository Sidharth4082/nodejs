pipeline {
  agent any
  environment {
    dockerHome = tool 'mydocker'
    mavenHome = tool 'Minstall'
    PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
  }
  
  stages {
    stage ('Build') {
      steps {
        sh 'docker build -p nodejs .'
      }
    }
    stage ('Run the build') {
      steps {
        sh 'docker run -p 5000:5000 nodejs'
      }
    }
  }
