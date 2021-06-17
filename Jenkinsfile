pipeline{
  agent any
  
  stages{
    stage('Build'){
      steps{
      echo 'Printing Hello world'
      javac HelloWorld.java
      java HelloWorld
      }
    }
    stage('Test'){
      steps{
        echo 'Testing'
      }
    }
  }

}
