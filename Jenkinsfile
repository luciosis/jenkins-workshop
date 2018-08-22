node {
   stage ('Hello'){
        echo 'Hello World'
   }
   stage ('Preparation'){
       checkout scm
   }
   stage ('Build'){
       sh 'docker run -i -v "$PWD:/usr/src/mymaven -w /usr/src/mymaven" --rm maven:3-jdk-8 ls && mvn test install clean package'
   }
   stage ('Results'){
        archiveArtifacts artifacts: 'target/gildedrose-*.jar', onlyIfSuccessful: true
   }

}  

