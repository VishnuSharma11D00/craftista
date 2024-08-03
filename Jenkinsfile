pipeline{
  agent any
  
  tools{
    maven 'Maven 3.8.7'  
  }
  stages
  {
    stage("Voting Build")
    {
      steps
      {
        echo 'compiling the voting app'
        dir('voting')
        {
          sh 'mvn compile'
        }
      }
    }
  }

  post{
    always{
      echo 'completed the pipeline for craftista...'
    }
  }
}
