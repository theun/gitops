pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // git@github.com:theun/gitops.git will replace by sed command before RUN
        git url: 'git@github.com:theun/gitops.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}