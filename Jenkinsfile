properties([pipelineTriggers([githubPush()])])
node('linux') {
    stage("Unit Tests") {
       git 'https://github.com/madh0002/java-project.git'
       sh 'ant -f test.xml -v'
    }
    stage("Build") {
       sh 'ant -f build.xml -v'
    }
    
}
