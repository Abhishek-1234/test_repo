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
        bat 'robocopy C:\\Users\\ABHISHEK\\.jenkins\\workspace\\test_repo_main C:\\Users\\ABHISHEK\\.jenkins\\workspace\\test_repo_main\\backup'
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