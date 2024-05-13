pipeline {
  agent any

  stages {

    stage ("Continous Dowload"){
      steps {
        git branch: 'main', url: 'git@github.com:ze-labo/seili_cicd.git'
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

  }
}
