node {
stage("Start"){
   echo 'Starting'
}
stage("checkout"){
node('linux') {
   echo 'checkout'
checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'a6d446c6-7a3f-4883-9b53-9d0742ce8608', url: 'https://github.com/mithunjeyakumar/newapp.git']]])
}
}
stage("Build"){
node('linux') {

   echo 'Build'
   sh '''cd /home/rps/mithun_slave/workspace/PipelineDemo
mvn clean package'''
}
}

stage("Publish"){
   echo 'Publish'
}
stage("deploy"){
build 'FirstTest'

}
stage("End of deploy"){
   echo "deployment end"

}
}
