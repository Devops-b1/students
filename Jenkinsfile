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
    stages {
        stage ('pull code') {
            steps {
                sh 'echo "code pulled suceessfully"'
                git branch: 'J2EE', url: 'https://github.com/shashirajraja/onlinebookstore.git'
                sh 'ls'
            }
        }
        
        stage ('build stage') {
            steps {
                sh 'sudo apt install maven -y'
                sh 'mvn clean package'
                echo "build stage is complete"
            }
        }
        stage ('test sonar analysis') {
            steps {
                sh 'mvn clean varify sonar:sonar -Dsonar.projectKey=second-org-b2-b3-key -Dsonar.organization=second-org-b2-b3-key -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=c8909b8bb08e38a054ba3b4ccb2673f46c2087e5'
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



//pipeline {
//    agent none
//    stages {
//        stage('Build'){
//            agent { label 'inbestment-agent'}
//            steps {
//                git credentialsId: 'GitHub', url: 'git@github.com:atulyw/ecom-service.git'
//                sh '''
//                curl -O https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.tar.gz
//                tar -xvf apache-maven-3.9.4-bin.tar.gz -C /opt
//                export PATH=$PATH:/opt/apache-maven-3.9.4/bin/
//                mvn clean package -DskipTests
//                '''
//                stash includes: '**/target/**.jar,deploy/deployment.yml', name: 'artifact'
//            }
//        }
//        stage('Push-Artifacts'){
//            agent { label 'node1'}
//            steps {
//                unstash 'artifact'
//                sh '''
//                cat << EOF > dockerfile
//FROM openjdk:11-jre-buster
//COPY target/eShopping-2.1.0.jar /opt/
//WORKDIR /opt
//ENTRYPOINT ["java","-jar","-Ddb.url=${DB_URL}","-Ddb.username=${DB_USERNAME}","-Ddb.password=${DB_PASSWORD}","-Dspring.profiles.active=${ACTIVE_PROFILE}","eShopping-2.1.0.jar"]
//EOF
//                aws ecr get-login-password --region eu-west-1 | docker login --username AWS --password-stdin 527745292178.dkr.ecr.eu-west-1.amazonaws.com
//                docker build -t eshopping-service .
//                docker tag eshopping-service:latest 527745292178.dkr.ecr.eu-west-1.amazonaws.com/eshopping-service:latest
//                docker push 527745292178.dkr.ecr.eu-west-1.amazonaws.com/eshopping-service:latest
//                '''
//            }
//        }
//        stage('Deploy'){
//            agent { label 'node1'}
//            steps {
//                unstash 'artifact'
//                sh '''
//                aws eks --region eu-west-1 update-kubeconfig --name inbestment-dev
//                kubectl apply -f deploy/deployment.yml
//                '''
//            }
//        }    
//    }
//}
//
////mysql -uroot -p
////mysql -h localhost -uroot -p 
//

//mysql -h 52.215.161.100 -uroot -p





