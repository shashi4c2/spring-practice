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
        sh 'scp "ForwardAgent=yes" target/*.jar ssh ansible@10.0.0.73:/home/ansible'
    }
}
