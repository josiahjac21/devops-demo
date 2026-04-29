pipeline {
  agent any
  stages {
    stage('Pull Code') {
      steps {
        git 'https://github.com/josiahjac21/devops-demo.git'
      }
    }
    stage('Deploy') {
      steps {
        sh '''
        docker rm -f web || true
        docker run -d -p 8082:80 -v $(pwd):/usr/share/nginx/html nginx
        '''
      }
    }
  }
}
