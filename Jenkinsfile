pipeline{

    agent any

    tools {nodejs "node"}

    parameters{
        string(name: "SPEC", defaultValue: "cypress/integration/**/**", description: "Enter the script path that you want to execute")
        choice(name: "BROWSER", choices:['edge'], description:"choose the browser where you want to execute your script")
    }
    
    stages{
        stage('Building'){
            steps{
               bat "npm i"
               bat 'npm run build'
            }
        }
        stage('Testing'){
            steps{
                
                bat "npx cypress run --browser ${BROWSER} --spec ${SPEC}"
            }
        }
        stage('Deploying'){
            steps{
                echo "Deploy the Application"
            }
        }
    }
   
};


// pipeline {
//     agent {
//     // this image provides everything needed to run Cypress
//     docker {
//       image 'cypress/base:16.13.2'
//     }
//   }
    
//     tools {nodejs "node"}
    
//    parameters {
//         string(name: 'SPEC', defaultValue: 'cypress/integration/**', description: 'Ej: cypress/integration/*.spec.js')
//         choice(name: 'BROWSER', choices: ['chrome', 'edge', 'firefox'], description: 'Pick the web browser you want to use to run your scripts')
//     }

//     stages {
//         stage('Dependencies') {
//             steps {
//                 sh 'npm i'
//             }
//         }
//         stage('Build') {
//             steps {
//                 sh 'npm run build'
//             }
//         }
// //          stage('Unit Tests') {
// //             steps {
// //                 sh 'npm run test'
// //             }
// //         }
//         stage('e2e Tests') {
//             steps {
//                sh 'npx cypress install'
//                 sh 'npx cypress run'
// //                 sh 'CYPRESS_CACHE_FOLDER=./tmp/Cypress yarn install'

// //                 sh 'CYPRESS_CACHE_FOLDER=./tmp/Cypress npx cy run [--params]'
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying....'
//             }
//         }
//     }
// }
