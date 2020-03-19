pipeline {
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean source:jar package'
      }
    }
    stage('Static Analysis') {
      steps {
        sh 'mvn findbugs:findbugs'
      }
    }
  } 
}
