/**
* Android Jenkinsfile
*/
node("android"){
  stage("Checkout"){
    checkout scm
  }

  stage("Build"){
    sh 'chmod +x ./gradlew'
    if (params.BUILD_CONFIG == 'release') {
      sh './gradlew clean assembleRelease' // builds app/build/outputs/apk/app-release.apk file
    } else {
      sh './gradlew clean assembleDebug' // builds app/build/outputs/apk/app-debug.apk
    }
  }

  stage("Scan"){
    println('Upload built binary to Kryptowire')
    sh './pushToKryptowire.sh'
  }
}