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