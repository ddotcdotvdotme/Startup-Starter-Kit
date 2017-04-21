# Making iOS App

iOS App Prototyping Tools
* [Draw User Flow Diagram](https://www.draw.io)
* [Sketch App](https://www.sketchapp.com)
* [Invision App](https://www.invisionapp.com)
* [iOS UI App Resources](https://www.sketchappsources.com/tag/ios.html)

# App Fundamentals

## Helpful Resources
* [Understanding Swift](http://guides.codepath.com/ios/Understanding-Swift) => This guide covers a majority of the Swift topics, to get start check out the sections on [arrays](http://guides.codepath.com/ios/Understanding-Swift#arrays), and [dictionaries](http://guides.codepath.com/ios/Understanding-Swift#dictionaries), and [working with JSON](http://guides.codepath.com/ios/Understanding-Swift#working-with-json).
* [Xcode Project Basics](http://guides.codepath.com/ios/Project-Basics) => As you start building apps, it's helpful to know about all different types of files that you'll be working with inside of an Xcode Project.

## Video Tutorials
* [Quickstart #1 - Basic Table View Setup](https://youtu.be/XvMcmNozy68?list=PLrT2tZ9JRrf742tAoln7wjPsCm8dmuYyv)
* [Quickstart #2 - Intro to API](https://youtu.be/6EpN_K2kIps?list=PLrT2tZ9JRrf742tAoln7wjPsCm8dmuYyv)
* [Quickstart #3 - Custom Cells](https://youtu.be/bzIksPK8ACA?list=PLrT2tZ9JRrf742tAoln7wjPsCm8dmuYyv)
* [Quickstart #4 - CocoaPods and 3rd Party Libraries](https://youtu.be/T8KbTOEhQC4?list=PLrT2tZ9JRrf742tAoln7wjPsCm8dmuYyv)

## Test it Yourself
* [Install Cocoa Pods](http://guides.codepath.com/ios/CocoaPods#installing-cocoapods) from the command line using Terminal. Cocoa Pods is a package manager for pulling in dependencies that we'll use in this assignment.
* **Network Request Snippet** Ensure you can hit the "Now Playing" endpoint in a browser. This shows the data we will be using from The Movies Database.
- Check out The Movies Database [documentation](https://developers.themoviedb.org/3/getting-started). We'll be using the ["Now Playing" endpoint](https://developers.themoviedb.org/3/movies/get-now-playing) as example for network request.
- Note: It's helpful to install the JSONView Chrome Extension to view the returned JSON more easily.
- Sample Request: https://api.themoviedb.org/3/movie/now_playing?api_key=a07e22bc18f5cb106bfe4cc1f83ad8ed
- [Network Programming Guide](http://guides.codepath.com/ios/Network-Programming)
```swift
let apiKey = "a07e22bc18f5cb106bfe4cc1f83ad8ed"
let url = URL(string: "https://api.themoviedb.org/3/movie/now_playing?api_key=\(apiKey)")!
let request = URLRequest(url: url, cachePolicy: .reloadIgnoringLocalCacheData, timeoutInterval: 10)
let session = URLSession(configuration: .default, delegate: nil, delegateQueue: OperationQueue.main)
let task: URLSessionDataTask = session.dataTask(with: request) { (data: Data?, response: URLResponse?, error: Error?) in
if let data = data {
if let dataDictionary = try! JSONSerialization.jsonObject(with: data, options: []) as? NSDictionary {
print(dataDictionary)
}
}
}
task.resume()
```
* [Showing a progress HUD](http://guides.codepath.com/ios/Showing-a-progress-HUD)
* [Pull to Refresh](https://guides.codepath.com/ios/Table-View-Guide#adding-pull-to-refresh)
* [Collection View](http://guides.codepath.com/ios/Collection-View-Guide)
* [Search Bar](http://guides.codepath.com/ios/Search-Bar-Guide)
* [Images fade in as they are loading](https://guides.codepath.com/ios/Working-with-UIImageView#fading-in-an-image-loaded-from-the-network)
* Check out the following sites that have helpful graphics
- [iconmonstr](http://iconmonstr.com/) - Free quality image icons for use in your apps
- [iconfinder](https://www.iconfinder.com/) - More free (and paid) icons
- [The Noun Project](http://thenounproject.com/) - Creative Commons and public domain iconography

# Navigation

## Helpful Resources


## Video Tutorials
* [Quickstart - Navigation and Passing Data](https://youtu.be/5YhyEwyzI-0?list=PLrT2tZ9JRrf4mZnCIDXI8sdSg2IxWoj3K)
* [Quickstart - Safely Getting Images](https://youtu.be/YDNhZKUuAmQ?list=PLrT2tZ9JRrf4mZnCIDXI8sdSg2IxWoj3K)
* [Quickstart - Working with Scroll Views](https://www.youtube.com/watch?v=t3WhxFTb2Kk?list=PLrT2tZ9JRrf4mZnCIDXI8sdSg2IxWoj3K&index=3)
* [Quickstart - Configuring Tab Bars](https://youtu.be/j_SanHW2t5A?list=PLrT2tZ9JRrf4mZnCIDXI8sdSg2IxWoj3K)

## Test it Yourself
* User can view details by tapping on a cell
* You'll need to set the content size of the UIScrollView](http://guides.codepath.com/ios/Scroll-View-Guide) to get it to scroll properly.
* Calling the [sizeToFit](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UIView_Class/index.html#//apple_ref/occ/instm/UIView/sizeToFit) method on the [UILabel](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UILabel_Class/index.html) will help figure out how much space the `overview` label needs to fit all the text.
* User can select from a tab bar
- If you are using a storyboard for your app, there isn't a good way to use the same UIViewController for multiple tabs of your UITabBarController. Instead, you might want to set up your [tab bar programmatically](http://guides.codepath.com/ios/Tab-Bar-Quickstart#programmatic-setup) and then use [this method](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIStoryboard_Class/#//apple_ref/occ/instm/UIStoryboard/instantiateViewControllerWithIdentifier:) to create instances of your view controllers.
* Customizing the [cell selection effect](http://guides.codepath.com/ios/Table-View-Guide#customizing-the-cell-selection-effect)
* Customizing the [navigation bar](http://guides.codepath.com/ios/Navigation-Controller#customizing-the-appearance-of-navigation-bar).
* Effective way to [load large image](https://guides.codepath.com/ios/Working-with-UIImageView#loading-a-low-resolution-image-followed-by-a-high-resolution-image).

# AutoLayout

## Video Tutorials
* [Understanding Mobile Architecture](http://courses.codepath.com/course_videos/ios_university/youtu/2prJ5dk4Nlo?title=Understanding+Mobile+Architecture) (14 minutes)
* [The Basics of AutoLayout](http://courses.codepath.com/course_videos/ios_university/youtu/xS48h1FcGAE?title=The+Basics+of+AutoLayout) (23 minutes)
* [AutoLayout for Labels](http://courses.codepath.com/course_videos/ios_university/youtu/XMHKgxqx-9k?title=AutoLayout+for+Labels) (20 minutes)
* [Quickstart - Yelp Basic Setup](http://courses.codepath.com/course_videos/ios_university/youtu/s0mET2vbpvE?title=Assignment+Quickstart+-+Yelp+Basic+Setup) (15 minutes)
* [Quickstart - Auto Layout of Restaurant Cell](http://courses.codepath.com/course_videos/ios_university/youtu/N6qkyMNTYAA?title=Assignment+Quickstart+-+Auto+Layout+of+Restaurant+Cell) (17 minutes)

## Test it Yourself
* You can download the [starter project](https://github.com/codepath/ios_yelp_swift) which has basic integration with Yelp.
* [Dynamic height](http://guides.codepath.com/ios/Table-View-Guide#variable-row-height) according to the content height.
* Proper [Auto Layout constraints](http://guides.codepath.com/ios/Auto-Layout-Basics).
* [Search Bar in Navigation View](http://guides.codepath.com/ios/Search-Bar-Guide#search-bar-in-navigation-view).
* [Infinite Scroll](http://guides.codepath.com/ios/Table-View-Guide#adding-infinite-scroll)
* [Map View](https://guides.codepath.com/ios/Maps)

# Networking + Authentication

## Video Tutorials
* [A Conceptual Look at OAuth](http://courses.codepath.com/course_videos/ios_university/youtu/tFYrq3d54Dc?title=A+Conceptual+Look+at+OAuth)
* [Twitter - Setup](https://youtu.be/4VQQTLybods?list=PLrT2tZ9JRrf7W4hoXt0cWHcvLRfvQlCKl) (28 minutes) 
* [Twitter - Models](https://youtu.be/LpJchnjdMwQ?list=PLrT2tZ9JRrf7W4hoXt0cWHcvLRfvQlCKl) (21 minutes)
* [Twitter - API Client](https://youtu.be/Do0FnfJDY6E?list=PLrT2tZ9JRrf7W4hoXt0cWHcvLRfvQlCKl) (28 minutes)
* [Twitter - Saving Current User](https://youtu.be/mjnz4sGe3Ps?list=PLrT2tZ9JRrf7W4hoXt0cWHcvLRfvQlCKl) (28 minutes)

# Animations + Gestures

## Video Tutorials
* [Animations](http://courses.codepath.com/course_videos/ios_university/youtu/ojVrgo9aQ94?title=Animations) (31 minutes)
* [Gestures](http://courses.codepath.com/course_videos/ios_university/youtu/SSwkKFrdw2A?title=Gestures) (25 minutes)
