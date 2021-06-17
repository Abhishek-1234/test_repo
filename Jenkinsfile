pipeline{
  agent any
  
  stages{
    stage('Build'){
      steps{
      echo 'Printing Hello world'
      }
      steps{
        bat '''javac HelloWorld.java
        java HelloWorld'''
      }
    }
    stage('Test'){
      steps{
        echo 'Testing'
      }
    }
  }

}
