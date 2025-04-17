pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'java17'
    maven 'maven3'
  }
  stages{
      stage("Cleanup Worksapce"){
        steps {
          cleanWs()
          }
      }
      stage("Checkout from SCM"){
        steps{
          git branch: 'main', credentialsId: 'github', url: 'https://github.com/Raghul0715/demo_repo'
           }
      }
      stage("Build App"){
        steps {
          sh "mvn clean package"
        }
      }
      stage("Test App"){
        steps {
          sh "mvn test"
        }
      }
  }
}