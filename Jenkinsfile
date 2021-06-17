pipeline{
  agent any
  
  stages{
    stage('Build'){
      steps{
      bat '''echo 'Printing Hello world'
      javac HelloWorld.java
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
