node {
  stage('SCM Checkout') {
    git branch: 'main', url: 'https://github.com/Sourav356/Jenkins_projects'
  }
  stage('compile - package') {
    def mvnHOME = tool name: 'Maven', type: 'maven'
    sh "${mvnHOME}/bin/mvn package"
  }
}

