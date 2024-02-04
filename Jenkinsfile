pipeline{
  agent any 
  tools {
    maven "maven"
  } 
  stages {
    stage('1 GetCode 1'){
      steps{
        sh "echo 'cloning the latest application version' "
        checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/clumumba/webapps-repo.git']]
       )
     }
  }
    
    stage('2 Test+ 3 Build'){
      steps{
        sh "echo 'running JUnit-test-cases' "
        sh "echo 'testing must passed to create artifacts ' "
        sh "mvn clean package"
      }
    }
    
    stage('4 CodeQuality'){
      steps{
        sh "echo 'Perfoming CodeQualityAnalysis' "
        sh "mvn sonar:sonar"
      }
    }
    /*
    stage('5 uploadNexus'){
      steps{
        sh "mvn deploy"
      }
    } 
    
}

  post{
    always{
      emailext body: '''Hey guys
Please check build status.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    }
    success{
      emailext body: '''Hey guys
Good job build and deployment is successful.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    } 
    failure{
      emailext body: '''Hey guys
Build failed. Please resolve issues.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    }
  } 
  */
}
