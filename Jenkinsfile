properties([parameters([choice(choices: ['master', 'main', 'feature'], description: 'Creating a parameterizes job', name: 'branch')])])
node {
  stage('SCM Checkout') {
    echo "Pulling changes from the branch ${params.branch}"
    git branch: params.branch, url: 'https://github.com/Sourav356/Jenkins_projects'
    
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

