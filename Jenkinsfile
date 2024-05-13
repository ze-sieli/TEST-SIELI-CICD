pipeline {
  agent any

  stages {

    stage ("Continous Dowload"){
      steps {
        git branch: 'main', url: 'https://github.com/ze-sieli/TEST-SIELI-CICD.git'
      }
    }

    stage ("Unit Test"){
      steps {
        sh 'mvn test'
      }
    }

    stage ("Integration Test"){
      steps {
        sh 'mvn verify -DskipUnitTests'
      }
    }

    stage ("Continuous build"){
      steps {
        sh 'mvn clean install'
      }
    }

    stage("static test analytic"){
      steps{
        script{
            withSonarQubeEnv(credentialsId: 'Sonar-token') {
                // some block
                sh'mvn clean package sonar:sonar'
                }
        }
      }
    }
  }
}
