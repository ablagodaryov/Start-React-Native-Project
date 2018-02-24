# iOS:

**'config.h' file not found** (third-party)
    http://www.programfaqs.com/faq/config-h-file-not-found-in-ios-project-of-react-native/

    Close Xcode.
    Open Terminal, go to your project’s root folder and do:
    cd node_modules/react-native/third-party/glog-0.3.4/
    Run the configure script:
    ./configure
    Open Xcode and try to run your app.

**"RCTBundleURLProvider.h" file not found`** (in AppDelegate.m)
    https://github.com/react-community/create-react-native-app/issues/316#issuecomment-351371080

    Product->Scheme->Manage Schemes click '+' at the Target to select "React" and set the React is shared.

# Common

### Splash screen:

##### Android
    Files for android splash should be named by this rules: File-based resource names must contain only lowercase a-z, 0-9, or underscore
    `Can't convert value at index 35 to color: type=0x1`
    https://github.com/crazycodeboy/react-native-splash-screen/issues/144#issuecomment-353243346
    
##### iOS
    In ios go to `images.xassets` right click in right menu -> add new image screen
    after add all screens -> go to project general settings -> App icons & Launch screens -> click on button in Launch image source picker -> choose images -> press migrate -> delete text in Launch screen file picker (need to clean and restart packager and xCode after that)


### React Navigation

**Tab navigator doesn't show tab content when language is RTL:**

Need to set `swipeEnabled: true` for TabNavigator: 
    `TabNavigator({...someRoutes}, { swipeEnabled: true })` 
