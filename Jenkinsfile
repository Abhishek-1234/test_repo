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
        bat 'robocopy C:\\Users\\ABHISHEK\\.jenkins\\workspace\\test_repo_main C:\\Users\\ABHISHEK\\.jenkins\\workspace\\test_repo_main\\backup & IF %ERRORLEVEL% LEQ 1 exit /B 0'
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