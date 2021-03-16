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
        sh 'ssh ansible@13.233.85.62'
        sh 'scp  ubuntu@13.232.248.136:target/*.jar ansible@13.233.85.62:/home/ansible'
    }
}
