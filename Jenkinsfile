node('maven'){
stage('maven define'){
   // use the id of the globally configured maven instance
def mvnTool = tool 'Apache Maven 3.6.2'

// execute maven
sh "${mvnTool}/bin/mvn clean install" 
junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site', reportFiles: 'index.html', reportName: 'HTMLReport', reportTitles: ''])sh "${mvnTool}/bin/mvn clean test surefire-report:report-only"   
   sh "echo hello world"
   }
stage('2nd stage'){
   sh "touch abc.txt"
   }
stage('3rd stage'){
   sh "echo sample in feature branch "
 }
}
