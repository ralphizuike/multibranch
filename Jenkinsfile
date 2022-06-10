pipeline{
     	agent any
     	stages{
     		stage('version'){
     			steps{
     				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHUB-CREDENTIALS', url: 'https://github.com/ralphizuike/multibranch.git']]])
     			}
     		}
     		stage('parallel-job'){
     			parallel{
     				stage('cpu-infor'){
     					steps{
     						sh 'lscpu'
     					}
     				}
     				stage('date'){
     					steps{
     						sh 'date'
     					}
     				}
     				stage('location'){
     					steps{
     						sh 'whoami'

     					}
     				}
     				stage('sub-job4'){
     					steps{
     						echo 'Dr Eng Ike'
     					}
     					
     				}
     			}

     		}
     		stage('codebuild'){
     			steps{
     				sh 'cat /etc/passwd'
     			}
     		}
             stage('parallel-job2'){
                 parallel{
                     stage('check'){
                         steps{
                             sh 'ps -ef'
                         }
                     }
                     stage('calander'){
                         steps{
                             sh 'cal 2025'
                         }
                     }
                     stage('lscpu'){
                         steps{
                             sh 'lscpu'
                         }
                     }
                     stage('list-info'){
                         steps{
                             sh 'ls'
                         }
                     }
                 }
             }
     	}
     }
