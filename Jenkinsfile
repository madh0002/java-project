properties([pipelineTriggers([githubPush()])])
node('linux') {
    stage("UnitTests") {
        sh 'ant -f -buildfile test.xml -v'
    }
    stage("Build") {
       sh 'ant -f build.xml -v'
    }
}
