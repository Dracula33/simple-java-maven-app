node(""){
    stage("Git checkout"){
        git branch: '**', changelog: false, poll: false, url: 'https://github.com/Dracula33/simple-java-maven-app.git'
        echo "${env.BRANCH_NAME}"
        echo "${env.TAG_NAME}"
        echo "${env.GIT_BRANCH}"
        echo "${env.BUILD_ID}"
    }
}
