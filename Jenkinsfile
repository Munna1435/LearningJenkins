pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        echo "Hello Build Number ${env.BUILD_NUMBER} and Build Id ${BUILD_ID}"
      }
    }
    stage('Test'){
      steps{
        echo 'Hello Testing'
      }
    }
  }
}
