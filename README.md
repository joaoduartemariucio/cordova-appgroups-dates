## Description

This plugin helps to share data between a hybrid application and a native extension it is easy and efficient if everything is set up correctly.

## Adding the Plugin ##

Use the Cordova CLI and type in the following command:

`cordova plugin add https://github.com/joaoduartemariucio/cordova-appgroups-dates`

## Sample Code

The Plugin is only for iOS.

## Settings AppGroup

It is necessary to configure the extension of the application as shown in the link below.

https://developer.salesforce.com/blogs/engineering/2017/02/using-ios-app-extensions-mobile-sdk.html

### Save in UserDefaults

    var options = {
          key: "foo",
          value: "bar",
          suite: "group.cats.catsAreAwesome"};

    window.AppGroupsUserDefaults.save(options,
      function() {
         // success
      }, function() {
        // failed
      });

### Load from UserDefaults

    var options = {
          key: "foo",
          suite: "group.cats.catsAreAwesome"};

    window.AppGroupsUserDefaults.load(options,
      function(result) {
       // success
       console.log("Result:", result)
      }, function() {
        // failed
      });
      
 ### Load in Today extention in Swift 
    
    let foo = UserDefaults(suiteName: "group.cats.catsAreAwesome")!.string(forKey: "token")
        print(foo)

 ### Load in Objective-C

    NSUserDefaults* userDefaults = [[NSUserDefaults alloc] initWithSuiteName:@"group.cats.catsAreAwesome"];
    NSString* value = [userDefaults stringForKey:@"token"];
    NSLog(@"token in group.cats.catsAreAwesome is '%@'", value);
    
