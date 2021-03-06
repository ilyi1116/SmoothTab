# SmoothTab

![Swift 3.x](https://img.shields.io/badge/Swift-3.x-blue.svg)
![Swift 4.x](https://img.shields.io/badge/Swift-4.x-orange.svg)
![iOS 9.0+](https://img.shields.io/badge/iOS-9.0+-green.svg)

![Preview](preview.png)

## Requirements

* iOS 9.0+
* Swift 3.x, 4.x
* Xcode 8+

## Installation

#### [CocoaPods](https://cocoapods.org/)

```ruby
pod 'SmoothTab'
```

## How to use

### Complete screen

To setup and customize the component you should create items with  `SmoothTabItem`.

```swift
// Set Smooth Tab View on UIView in stroyboard
@IBOutlet weak var smoothTabView: SmoothTabView!

// Or create it without storyboard
let smoothTabView = SmoothTabView()
self.addSubview(smoothTabView)

let items: [SmoothTabItem] = [...]

// For configuring styles create new SmoothTabOptions
var options = SmoothTabOptions()
options.titleColor = UIColor.white
options.titleFont = .systemFont(ofSize: 16)
options.shadow = .default

// Finally call setup smoothTabView with items, options and give delegate
smoothTabView.setup(with: items, options: options, delegate: self)
```

You can customize views with options `SmoothTabOptions, SmoothTabShadowOptions`:
```swift

/// For set corner radius to selected view
///
/// - rounded: for calculating rounded view
/// - fixed: fixed corner radius with corner option
public enum CornerRadius {
	case rounded
	case fixed(corner: CGFloat)
}

public struct SmoothTabOptions {

	/// Tabs parent view options
	public var backgroundColor: UIColor
	public var imageContentMode: UIViewContentMode
	public var itemsMargin: CGFloat
	public var shadow: SmoothTabShadowOptions?

	/// Selected View Options
	public var titleFont: UIFont
	public var titleColor: UIColor
	public var cornerRadius: CornerRadius
	public var borderWidth: CGFloat
	public var borderColor: UIColor
	public var innerPadding: CGFloat
	public var imageTitleMargin: CGFloat

}

public struct SmoothTabShadowOptions {

	public var color: UIColor
	public var offset: CGSize
	public var opacity: Float
	public var radius: CGFloat

}
```

For tab selection action please implement  `SmoothTabDelegate`:

```swift
@objc public protocol SmoothTabDelegate: class {
    func smootItemSelected(at index: Int)
}
```

## Support

Feel free to [open issuses](https://github.com/yervandsar/SmoothTab/issues/new) with any suggestions, bug reports, feature requests, questions.

## Let us know!

We’d be really happy if you sent us links to your projects where you use our component. Just send an email to yervandsar@gmail.com And do let us know if you have any questions or suggestion regarding the animation.


### License

The MIT License (MIT)

Copyright (c) 2018 Yervand

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
