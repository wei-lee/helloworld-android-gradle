/**
* Android Jenkinsfile
*/
node("android"){
  stage("Checkout"){
    checkout scm
  }
  stage("Build"){
    sh 'chmod +x ./gradlew'
    sh './gradlew clean assembleDebug' // builds app/build/outputs/apk/app-debug.apk
  }

  stage("Scan"){
    println('Upload binary to Kryptowire for security scan')
  }
}
