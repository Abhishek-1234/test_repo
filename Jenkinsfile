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
        
        stage('Map.Binaries') {
          agent{
            label 'node_one'
          }
          steps {
            bat 'robocopy C:\\Users\\ABHISHEK\\Desktop\\ %cd% file_1.txt & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('Map.MDD') {
          agent{
            label 'node_two'
          }
          steps {
              
            bat 'robocopy C:\\Users\\ABHISHEK\\Desktop\\ %cd% file_2.txt & IF %ERRORLEVEL% LEQ 1 exit /B 0'
          }
        }

        stage('Map.Metafiles') {
          agent{
              label 'node_four'
            }
            steps {
            
            bat 'robocopy C:\\Users\\ABHISHEK\\Desktop\\ %cd% file_3.txt & IF %ERRORLEVEL% LEQ 1 exit /B 0'
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
