pipeline {
    agent any

    stages {
     
        
        stage('codeql') {
          steps{
        withCodeQL(codeql:'codeql') {
            withCredentials([string(credentialsId: 'github-token', variable: 'GITHUB_TOKEN')]) {
    // some block 
            sh 'ls -la'
            sh 'codeql --version'
            sh 'codeql database create dvna --language=javascript --overwrite'
          //sh 'codeql database analyze dvna javascript-code-scanning.qls --sarif-category=javascript --format=sarif-latest --output=dvna.sarif'
            sh 'codeql database analyze dvna javascript-code-scanning.qls --sarif-category=javascript --format=csv'    
                //using the rules installed, analyse the goof app to see results and output in SARIF
            sh 'ls -la'
          //  sh 'cat /var/jenkins_home/workspace/dvna/dvna.sarif'
            sh 'pwd'
           // sh 'codeql github upload-results --repository=myvali95/dvna-1 --ref=master --commit=aad705823db8c3bedf9f2e65eb2dd5346ebf9307 --sarif=dvna.sarif'
    
                
            }
            
            
         
         
         }
         }
        }
       
    }
}
