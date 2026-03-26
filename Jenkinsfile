node {
  stage('SCM Checkout') {
    git branch: 'main', url: 'https://github.com/Sourav356/Jenkins_projects'
  }
  stage('compile - package') {
    def mvnHOME = tool name: 'Maven', type: 'maven'
    sh "${mvnHOME}/bin/mvn package"
  }
  stage ('Email Notification'){
    mail bcc: '', body: ''' Hi Sourav,

Your Jenkins job is executed successfully.

Thanks & Regards

Sourav Mallick.''', cc: '', from: '', replyTo: '', subject: 'Jenkins Email Notification Service', to: 'mallicksourav487@gmail.com'
  }
  stage ( 'Slack Notification'){
    slackSend baseUrl: 'https://hooks.slack.com/services/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/', channel: 'jenkins-project', color: 'good', message: 'Hi Sourav, Welcome to world of slack'
  }
}

