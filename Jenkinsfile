pipeline{
  agent{label 'Jenkins-Agent'}
  tools{
    jdk 'java17'
    maven 'Maven3'
  }
  stages{
    stage("cleanup workspace"){
      steps{
        cleanws()
      }
    }
    stage("Checkout from scm"){
      steps{
        git branch:'master', credentialsId:'github', url:'https://github.com/Harish5735/Project_demo'
      }
    }
    stage("Build Application"){
      steps{
        sh "mvn clean package"
      }
    }
    stage("Test Application"){
      steps{
        sh "mvn test"
      }
    }
  }
}
