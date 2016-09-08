# CCLabel

Fast implementation of [connected-component labelling](https://en.wikipedia.org/wiki/Connected-component_labeling) in Swift. 
Currently only 4-connectivity is supported. 

In `CcLabel`, call the `labelImageFast` function to label your image. Optionally, the bounding boxes of the components can be 
computed by passing-in `true` for the `calculateBoundingBoxes` parameter.

NOTE: Before processing, the image must first be binarized (all pixels must be either black or white). 
To binarize an image using the [GPUImage](https://github.com/BradLarson/GPUImage) library:

```swift
class func binarizeImage(image: UIImage) -> UIImage {
    let start = NSDate()
    let stillImageFilter = GPUImageAdaptiveThresholdFilter()
    stillImageFilter.blurRadiusInPixels = 4.0
    let filteredImage = stillImageFilter.imageByFilteringImage(image)
    let end = NSDate();
    print("Binarized image in " + String(end.timeIntervalSinceDate(start)) + " seconds")
    return filteredImage
}
```

## TODO

 * Automated tests
 * Better documentation
 * Code tidy-up (break long methods up a bit)
 * Performance results
 * 8-connectivity

# License

CCLabel is licensed under the [Apache License, Version 2.0](LICENSE.md)