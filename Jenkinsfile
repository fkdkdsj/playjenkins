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
          echo "hello"
          sh "hostname"
          kubernetesDeploy(configs: ["nginx.yaml","test.yaml"], kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
