pipeline {
  agent any
  stages {
    stage('Echo Version') {
      steps {
        sh 'echo Print Maven Version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        git(branch: 'main', url: 'https://github.com/omarghonim1/jenkins-hello-world.git')
        sh 'mvn clean package -DskipTests=true'
      }
    }

    stage('Unit Test') {
      steps {
        sh 'mvn test'
      }
    }

  }
  tools {
    jdk 'JDK17'
    maven 'M3911'
  }
}