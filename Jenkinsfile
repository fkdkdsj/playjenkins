pipeline {

  agent { label 'jenkins-agent' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/fkdkdsj/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
