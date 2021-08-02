pipeline {
    agent any

    stages {
     
        
        stage('codeql') {
          steps{
        withCodeQL(codeql:'codeql') {
            sh 'ls -la'
            sh 'codeql --version'
            sh 'codeql database create dvna --language=javascript --overwrite'
            sh 'codeql database analyze dvna javascript-code-scanning.qls --sarif-category=javascript --format=sarif-latest --output=webgoat.sarif' //using the rules installed, analyse the goof app to see results and output in SARIF
         
         }
         }
        }
       
    }
}
