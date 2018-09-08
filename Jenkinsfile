node {
   stage('SCM_checkout') {
            steps {
              git url: "https://github.com/devops98/game-of-life.git", branch: 'master'
            }
        }

   
   try {
    stage 'Build'
    sh "${Maven_Home}/bin/mvn clean install"
   
    stage 'Archive'
    archiveArtifacts  'target/gameoflife/gameoflife-deploy/gameoflife.war'
   } catch (err) {
    emailext body: 'Hi, your build successfully failed', subject: 'Test jenkins', to: 'test@gmail.com'
   }
}
