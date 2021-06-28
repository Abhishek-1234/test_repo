pipeline {
    
  agent any
  
  stages {
    stage('Fetch.Changes') {
      steps {
        bat 'g++ -o main.exe Hello.cpp'
        bat '.\\main.exe'
      }
    }

    stage('Parallel Stages') {
      parallel {
        stage('Parallel_1') {
          steps {
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_one'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_one main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('Parallel_2') {
          steps {
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_two'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_two main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('Parallel_3') {
          steps {
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_three'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_three main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

      }
    }

    stage('Run.Smoke') {
      steps {
        bat '.\\main.exe'
      }
    }

  }
}
