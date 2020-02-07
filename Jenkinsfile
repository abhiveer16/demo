pipeline {
  agent {
    node {
      label 'master'
    }
  }

  options {
    skipDefaultCheckout()
    timestamps()
  }

  stages {

    stage("Code Checkout") {
      steps {
        deleteDir()
        git 'https://github.com/abhiveer16/demo.git'
      }
    }

    stage("Java App - 1") {
      when {
        allOf {
            branch 'master'; changeset pattern: "java-app-1/**/*.java"
        }
      }
      steps {
        println "java app -1"
      }
    }

    stage("Node App - 1") {
      when {
        allOf {
            branch 'master'; changeset pattern: "node-app-1/**/*.js"
        }
      }
      steps {
        println "Node app - 1"
      }
    }
  }
  
}
