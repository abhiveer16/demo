pipeline {
  agent {
    node {
      label 'ci-slave-linux'
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
        git 'https://github.com/Aamir010/new-repo.git'
      }
    }

    stage("Java App - 1") {
      when {
        allOf {
            branch 'master'; changeset glob: "java-app-1/**/*.java"
        }
      }
      steps {
        println "java app -1"
      }
    }

    stage("Node App - 1") {
      when {
        allOf {
            branch 'master'; changeset glob: "node-app-1/**/*.js"
        }
      }
      steps {
        println "Node app - 1"
      }
    }
  }
  
}
