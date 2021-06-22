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
        bat 'mkdir C:\\users\\abhishek\\desktop\\backup'
        bat 'robocopy %cd% C:\\Users\\ABHISHEK\\desktop\\backup & IF %ERRORLEVEL% LEQ 1 exit /B 0'
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