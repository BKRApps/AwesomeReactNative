# AwesomeReactNative
http://blog.teamtreehouse.com/install-node-js-npm-mac

1.install Homebrew a Package manager for Mac
    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
2.if it required xcode command line tools then
    xcode-select --install
3.to check everything is up and ready
    brew doctor
4.install node
    brew install node
5.sudo chown -R $(whoami) $(brew --prefix)/*
6.npm install -g react-native-cli
7.brew install watchman 

1.react-native init <Project Name>
2.react-native run-ios
3."myPort" : "react-native start --port "  in scripts in package.json and do npm run myPort and change the port in xcode project.
https://github.com/facebook/react-native/issues/10715
4.build the bundle.
"build:ios": "react-native bundle --entry-file='index.js' --bundle-output='./ios/AwesomRNProject/main.jsbundle' --dev=false --platform='ios' --assets-dest='./ios'"

5. When the local server is not running, it will be loading the bundle from main.jsbundle,
   otherwise it will load from the jsCodeLocation "http://localhost:9988/index.bundle?platform=ios&dev=true&minify=false".

6. Both ironically take the bundle from the same command line. 
   jsCodeLocation = [[RCTBundleURLProvider sharedSettings] jsBundleURLForBundleRoot:@"index123" fallbackResource:nil];
   then it will look for index123 file and then build the bundle with the same name. it would be like this.

   react-native bundle --entry-file='index123.js' --bundle-output='./ios/AwesomRNProject/index123.jsbundle' --dev=false --platform='ios' --assets-dest='./ios
