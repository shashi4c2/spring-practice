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
    stage('copyjarfile') {
        sh 'scp ubuntu@13.233.237.227:target/*.jar  ubuntu@13.233.149.170:/home/ubuntu/'
    }
}
