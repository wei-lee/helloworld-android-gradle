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

  stage("Archive"){
    archiveArtifacts artifacts: '**/*.apk', excludes: 'app/build/outputs/apk/*-unaligned.apk'
  }
}
