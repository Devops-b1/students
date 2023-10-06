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


// pipeline {
//     agent {
//         label 'linux'
//     }
//     stages {
//         stage ('pull code') {
//             steps {
//                 sh 'echo "code pulled suceessfully"'
//                 git branch: 'main', url: 'https://github.com/Devops-b1/devsecops-jenkins-k8s-tf-sast-sonarcloud-repo.git'
//                 sh 'ls'
//             }
//         }
//         stage ('build stage') {
//             steps {
//                 echo "bulid artifact succesfully"
//             }
//         }
//         stage ('test stage') {
//             steps {
//                 echo "report save successfully"
//             }
//         }
//         stage ('deploy stage') {
//             steps {
//                 echo "app depoly successfully"
//             }
//         }

//     }
// }


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


pipeline {
    agent any
    stages {
        stage ('usevariable') {
            steps {
                echo "jenkis home is ${JENKINS_HOME}"
                echo "node name is ${NODE_NAME}"
            }
        }
    }
}

