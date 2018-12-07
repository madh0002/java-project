properties([pipelineTriggers([githubPush()])])
node('linux') {
    stage("Build") {
       git 'https://github.com/madh0002/java-project.git'
       sh 'ant -f build.xml -v'
    }
}
