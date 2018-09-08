node {
   stage('Build'){
            steps {
                sh 'mvn clean package'
            }

   }
   try {
    stage 'Build'      {
       steps {
    sh "${Maven_Home}/bin/mvn clean install"
      }
    }
    stage 'Archive'      {
    steps {
    archiveArtifacts  'target/gameoflife/gameoflife-deploy/gameoflife.war'
   } 
       catch (err) {
    emailext body: 'Hi, your build successfully failed', subject: 'Test jenkins', to: 'test@gmail.com'
   }
   }
}

