pipeline {
    
  agent none
  
  stages {
      
    stage('Fetch.Changes') {
      agent{
              label 'node_one'
      }  
      steps {
        
        bat 'g++ -o main.exe Hello.cpp'
        bat '.\\main.exe'
      }
    }

    stage('Parallel Stages') {
      parallel {
        
        stage('Parallel_1') {
          agent{
            label 'node_one'
          }
          steps {
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_one'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_one main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('Parallel_2') {
          agent{
            label 'node_two'
          }
          steps {
              
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_two'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_two main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('Parallel_3') {
          steps {
            agent{
              label 'node_three'
            }
            bat 'mkdir C:\\Users\\ABHISHEK\\Desktop\\backup_three'
            bat 'robocopy %cd% C:\\Users\\ABHISHEK\\Desktop\\backup_three main.exe & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

      }
    }

    stage('Run.Smoke') {
      agent{
        label 'node_one'
      }
      steps {
        bat '.\\main.exe'
      }
    }

  }
}
