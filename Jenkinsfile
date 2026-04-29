pipeline {
  agent any
  stages {
    stage('Pull Code') {
      steps {
        git branch: 'main', url: 'https://github.com/josiahjac21/devops-demo.git'
      }
    }
    stage('Deploy') {
      steps {
        sh '''
        docker rm -f web || true
        docker run -d --name web -p 8082:80 nginx
        '''
      }
    }
  }
}
