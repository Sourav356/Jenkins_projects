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

    slackSend channel: 'jenkins-project', color: 'good', message: 'Hello everyone, I have successfully set up the slack notification.', teamDomain: 'devops-ho96143', tokenCredentialId: 'slack_jenkins'
     
  }
}

