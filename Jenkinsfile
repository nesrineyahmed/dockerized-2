pipeline {
    agent { dockerfile true }
   
    tools {nodejs "nodejs"}
    
    stages{
        
        stage ("Install dependenciess"){
            steps{
                echo "installing dependencies"
                sh "npm i npm@latest -g"
                sh "cd the-example-app.nodejs && npm install"
            }
        }
        stage ("Deploy"){
            steps{
                echo "start project"
                sh "cd the-example-app.nodejs && npm run start:dev &"
            }
        }
        stage ("Test"){
            steps{
                echo "verify"
                sh "curl http://localhost:3000" 
            }
        }

    }
    
}
