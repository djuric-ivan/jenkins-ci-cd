// pipeline {
//     agent any
//
//     tools {
//         maven "maven"
//         jdk "jdk_22"
//     }
//
//     stages {
//         stage("SCM checkout") {
//             steps {
//                 checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/djuric-ivan/jenkins-ci-cd']])
//             }
//         }
//         stage("Build Process") {
//             steps {
//                 script {
//                     bat 'mvn clean install'
//                 }
//             }
//         }
//         stage("Build Docker Image"){
//             steps {
//                 script {
//                     bat 'docker build -t ivandjuric43/spring-cicd:1.0'
//                 }
//             }
//         }
//     }
//
//     post {
//         always {
//             emailext attachLog: true,
//                      body: '''<!DOCTYPE html>
//                      <html lang="en">
//                         <head>
//                             <meta charset="UTF-8">
//                             <meta name="viewport" content="width=device-width, initial-scale=1.0">
//                             <title>Build Notification</title>
//                             <style>
//                                 body { font-family: Arial, sans-serif; margin: 20px; }
//                                 .container { border: 1px solid #ccc; padding: 20px; border-radius: 5px; background-color: #f9f9f9; }
//                                 .header { font-size: 24px; font-weight: bold; margin-bottom: 10px; }
//                                 .status { font-size: 18px; color: #333; }
//                                 .link a { color: #1a73e8; text-decoration: none; font-weight: bold; }
//                             </style>
//                         </head>
//                         <body>
//                             <div class="container">
//                                 <div class="header">Build Notification</div>
//                                 <div class="status">
//                                     <p>Build Number: <strong>${BUILD_NUMBER}</strong></p>
//                                     <p>Status: <strong>${currentBuild.currentResult}</strong></p>
//                                 </div>
//                                 <div class="link">
//                                     <p>Details: <a href="${BUILD_URL}" target="_blank">View Build</a></p>
//                                 </div>
//                             </div>
//                         </body>
//                     </html>
//                     ''',
//                     mimeType: 'text/html',
//                     replyTo: 'ivandjuric433@gmail.com',
//                     subject: 'Pipeline status : ${BUILD_NUMBER}',
//                     to: 'ivandjuric433@gmail.com'
//         }
//     }
// }