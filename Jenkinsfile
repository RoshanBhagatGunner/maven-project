pipeline {
    agent any
    stages{
        stage('Performance Tests') {
            steps {
                sh "bzt test_jmxScript.yml -report -o settings.artifacts-dir=artifacts"
            }
    }

    stage("post-proc") {
        steps {
            
            archiveArtifacts artifacts: 'artifacts/*.log'
            junit 'artifacts/xunit.xml'
        }
    }
     
    }
    
    
      
}
