node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'mvn';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn verify sonar:sonar -Dsonar.projectKey=Simp_Quality_Project_Sonnar -Dmaven.test.failure.ignore=true"
    }
  }
}
