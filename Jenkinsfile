/**
* Android Jenkinsfile
*/
node("android"){
  stage("Checkout"){
    checkout scm
  }

  stage ("Prepare"){
    println("Prepare")
  }

  stage("Build"){
    sh 'chmod +x ./gradlew'
    sh './gradlew clean assembleDebug' // builds app/build/outputs/apk/app-debug.apk
  }

  stage("Sign"){
    println('Debug Build - Using default developer signing key')
  }
  
  stage("Security Scan"){
    println('Upload binary to Kryptowire for security scan')
  }

  stage("Archive"){
    archiveArtifacts artifacts: '**/*.apk', excludes: 'app/build/outputs/apk/*-unaligned.apk'
  }
}
