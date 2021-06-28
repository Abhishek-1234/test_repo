pipeline {
    
  agent any
  
  stages {
    stage('Build') {
      steps {
        bat 'g++ -0 main.exe Hello.cpp'
        bat '.\\main.exe'
      }
    }

    stage('Parallel1') {
      parallel {
        stage('Parallel1') {
          steps {
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_one'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_one main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('parallel2') {
          steps {
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_two'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_one main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('parallel3') {
          steps {
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_three'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_one main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

      }
    }

    stage('smoke') {
      steps {
        bat '.\\main.exe'
      }
    }

  }
}
