#!groovy

node('master') {

  // A collection of build utils.
  def utils = load "/scripts/buildUtils.groovy"

  stage ('Extract') {
    checkout scm
  }

  stage ('Build') {
    utils.mavenBuild ('clean', 'package')
    utils.dockerBuild ('microservice-vote')
  }

  stage ('Deploy') {
    utils.deploy ()
  }

}