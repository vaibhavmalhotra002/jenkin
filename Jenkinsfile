//CODE_CHANGES = getGitChanges()
pipeline{
  agent any  
    // environment{
    //   NEW_VERSION ='1.3.0'//Declare env. variables here which can be used anywhere in jenkins file
    //   // SERVER_CREDENTIALS= credentials('Server-credential')
    // }

    // tools{
    //   maven "Maven"
    //   // gradle
    //   // jdk
    // }

    parameters{
      // string(name: 'VERSION' , defaultValue: '', description:'version to deploy on prod')
      choice(name: 'VERSION' , choices:['1.1.0' , '1.2.0' , '1.3.0'], description: '')
      booleanParam(name: 'executeTests', defaultValue:true,description '')
    }

  stages{
    stage("Build") {
      steps {
        echo 'Building the application..'
        // echo "Building version ${NEW_VERSION}"
        // sh "mvn install"
      }
    }
    stage("test") {
        // when{
        //     expression{
        //         BRANCH_NAME=='dev' && CODE_CHANGES= true
        //     }
        // }
        when{
          expression{
            params.executeTests == true
          }
        }
      steps {
         echo 'testing the application..'
      }
    }
    stage("Deploy") {
      steps {
         echo 'Deploying the application..'
        // using nev variable in one place only
        //  withCredentials([
        //   usernamePassword(credentials:'Server-credential',usernameVariable:USER, passwordVarialbe:PWD)
        //  ]){
        //      sh "Some Script ${USER} ${PWD}"
        //  }
        echo "Deploying version ${params.VERSION}"
      }
    }
  }
}
    
        
