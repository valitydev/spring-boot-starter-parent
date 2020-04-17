#!groovy
build('spring-boot-starter-parent', 'docker-host') {
    checkoutRepo()
    loadBuildUtils()

    def javaLibPipeline
    runStage('load JavaLib pipeline') {
        javaLibPipeline = load("build_utils/jenkins_lib/pipeJavaLib.groovy")
    }

    ef serviceName = env.REPO_NAME
    def mvnArgs = '-DjvmArgs="-Xmx256m"'
    def useJava11 = true
    def registry = 'dr2.rbkmoney.com'
    def registryCredsId = 'jenkins_harbor'

    javaServicePipeline(serviceName, useJava11, mvnArgs, registry, registryCredsId)
}

