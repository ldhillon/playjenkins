pipeline {

  agent { label 'mykubepod' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/ldhillon/playjenkins.git', branch:'test-deploy-stage'
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
