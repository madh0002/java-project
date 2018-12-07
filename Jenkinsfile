properties([pipelineTriggers([githubPush()])])
node('linux') {
    stage("Unit Tests") {
       git 'https://github.com/madh0002/java-project.git'
       sh 'ant -f test.xml -v'
    }
    stage("Build") {
       sh 'ant -f build.xml -v'
    }
    stage("Deploy") {
       sh 'aws s3 cp *.jar s3://madhu-assignment10-bucket/.'
    }
    stage("Report") {
       sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
    }
}
