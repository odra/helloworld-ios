node('ios') {
  stage('Checkout') {
    checkout scm
  }

  stage('Prepare') {
    sh 'pod install'
  }

  stage('Build') {
    xcodeBuild(
      cleanBeforeBuild: true,
      src: 'helloworld-ios',
      schema: 'helloworld-ios-app',
      workspace: 'helloworld-ios-app',
      buildDir: 'build',
      bootstrapKeychain: true,
      sdk: 'iphoneos',
      version: '0.1-apha',
      shortVersion: '0.1',
      bundleId: 'com.feedhenry.helloworld-ios-app',
      infoPlistPath: 'helloworld-ios-app-Info.plist',
      flags: '-fstack-protector -fstack-protector-all',
      autoSign: false
    )
  }

  stage ('Codesign') {
    println('Codesign')
  }

  stage ('Archive') {
    println('Archive')
  }
}