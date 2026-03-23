node {
  stage('SCM Checkout') {
    git branch: 'main', url: 'https://github.com/Sourav356/Jenkins_projects'
  }
  stage('compile - package') {
    sh 'mvn package'
  }
}

