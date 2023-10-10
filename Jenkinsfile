// #pipeline {
// #   agent any
// #   stages {
// #       stage ('pull code') {
// #           steps {
// #               sh 'echo "code pulled suceessfully"'
// #               git branch: 'main', url: 'https://github.com/Devops-b1/devsecops-jenkins-k8s-tf-sast-sonarcloud-repo.git'
// #               sh 'ls'
// #           }
// #       }
// #       stage ('build stage') {
// #           steps {
// #               echo "bulid artifact succesfully"
// #           }
// #       }
// #       stage ('test stage') {
// #           steps {
// #               echo "report save successfully"
// #           }
// #       }
// #       stage ('deploy stage') {
// #           steps {
// #               echo "app depoly successfully"
// #           }
// #       }
// #
// #   }
// #}


pipeline {
    agent any
    tool {
        maven 'maven'
        jdk 'java'
    }

    stages {
        stage ('pull code') {
            steps {
                sh 'echo "code pulled suceessfully"'
                git branch: 'J2EE', url: 'https://github.com/shashirajraja/onlinebookstore.git'
                sh 'ls'
            }
        }
        stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
        stage ('build stage') {
            steps {
                dir("/var/lib/jenkins/workspace/demo-pipeline-1") {
                sh 'mvn -B -DskipTests clean package'
                }
            }
        }
        stage ('test stage') {
            steps {
                echo "report save successfully"
            }
        }
        stage ('deploy stage') {
            steps {
                echo "app depoly successfully"
            }
        }
    }   
}


// pipeline {
//     agent {
//         label 'linux'
//     }
//     stages {
//         stage ('print variables') {
//             steps {
//                 sh 'printenv'
//             }
//         }
//     }
// }


//pipeline {
//    agent any
//    stages {
//        stage ('usevariable') {
//            steps {
//                echo "jenkis home is ${JENKINS_HOME}"
//                echo "node name is ${NODE_NAME}"
//            }
//        }
//    }
//}

//pipeline {
//    agent any
//    environment {
//        customerip = "192.169.0.16" 
//    }
//    stages {
//        stage ('usevariable') {
//            steps {
//                echo "jenkis home is ${JENKINS_HOME}"
//                echo "node name is ${NODE_NAME}"
//                echo "customerip is ${customerip}"
//            }
//        }
//    }
//}







