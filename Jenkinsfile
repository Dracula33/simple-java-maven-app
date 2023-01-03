node(""){
    
    stage("Git checkout"){
        git branch: '**', changelog: false, poll: false, url: 'https://github.com/Dracula33/simple-java-maven-app.git'
        print(env.BRANCH_NAME)
        print(env.TAG_NAME)
        print($GIT_BRANCH)
    }
    stage("Maven"){
        b_name=env.BRANCH_NAME
        t_name=env.TAG_NAME
        print(t_name)
        print(b_name)
        VERSION=t_name.substring(t_name.lastIndexOf("/") + 1)
        if (VERSION == ''){
          VERSION=b_name.substring(b_name.lastIndexOf("/") + 1)
          if ( VERSION == "master" ){
            echo "Master branch must have a tag"
            sh 'exit 1'
          }
          sh "/opt/maven/bin/mvn -f ./pom.xml -s /var/lib/jenkins/workspace/test/settings.xml clean deploy -Dversion=$VERSION"
        }
        else{
            echo 'Version is EMPTY'
        }
        
    }
}
