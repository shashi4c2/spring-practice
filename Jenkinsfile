node('master') {
    stage('GIT') {
        git 'https://github.com/shashi4c2/spring-practice.git'
    }
    stage('package') {
        sh 'mvn package'
    }
    stage('archiveartifacts') {
        archive 'target/*.jar'
    }
    stage('archivetestresults') {
        junit 'target/surefire-reports/*.xml'
    }
    stage('copyfiles') {
        sh 'ssh-add'
        sh 'scp -v -o "ForwardAgent=yes" target/*.jar ubuntu@13.232.13.168:/home/ubuntu'
    }
}
