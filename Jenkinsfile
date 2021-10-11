pipeline {

  agent { label 'base' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'http://github.com/fkdkdsj/playjenkins', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          echo "hello"
          sh "hostname"
          sh "cat /etc/issue"
          sh "ip addr"
         
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
          kubernetesDeploy(configs: "test.yaml", kubeconfigId: "mykubeconfig")
          echo "====== Finished: SUCCESS ======"
        }
      }
    }

  }

}
