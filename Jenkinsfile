#!groovy

node('master') {

  def utils = load "/scripts/buildUtils.groovy"

  stage ('Extract') {
    checkout scm
  }

  stage ('Build') {
    utils.mavenBuild ('clean', 'package')
    utils.dockerBuild('libertyproject')
  }

  stage ('Deploy') {
    utils.deploy ()
  }