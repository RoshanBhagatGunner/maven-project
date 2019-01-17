pipeline {
    agent any
    stages{
        stage('Performance Tests') {
            bzt "test.yml -report -o settings.artifacts-dir=artifacts"
    }

    stage("post-proc") {
        archiveArtifacts artifacts: 'artifacts/*.log'
        junit 'artifacts/xunit.xml'
    }
     
    }
    
    
      
}
