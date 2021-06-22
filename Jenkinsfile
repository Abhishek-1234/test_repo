pipeline {
  agent any
  stages {
    stage('\'Build\'') {
      steps {
        bat 'g++ -o main.exe Hello.cpp'
      }
    }

    stage('Backup') {
      steps {
        bat 'mkdir backup'
        bat 'robocopy c:\\users\\abhishek\\.jenkins\\workspace\\ c:\\users\\abhishek\\.jenkins\\workspace\\backup'
      }
    }

    stage('Running') {
      steps {
        bat '.\\main.exe'
      }
    }

  }
  environment {
    stage = '\'Backup\''
  }
}