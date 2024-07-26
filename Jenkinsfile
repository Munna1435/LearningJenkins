pipeline{
  agent any

  parameters{
    choice(name: 'BUILD_NUMBER_CHOICE', choices: ['Auto', 'Manual'], description: 'Select the choice you wanna to increament the build number')
    string(name: 'MANUAL_BUILD_NUMBER', defaultValue: '1', description: 'Enter the build number')
  }

  stages{

    stage('Setup'){
      steps{
        script{
          getBuildNumber = {
            if(params.BUILD_NUMBER_CHOICE == "Auto")
            {
              echo "Auto ${env.BUILD_NUMBER}"
              return env.BUILD_NUMBER
            }
            echo "Manual ${env.BUILD_NUMBER}"
            return env.MANUAL_BUILD_NUMBER
          }
        }
      }
    }

    stage('Build'){
      steps{
        echo "Hello Build Number ${env.BUILD_NUMBER} and Build Id ${env.BUILD_ID}"
        echo getBuildNumber()
      }
    }

    stage('Test'){
      steps{
        echo 'Hello Testing'
      }
    }
  }
}
