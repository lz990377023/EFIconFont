![](https://github.com/EFPrefix/EFIconFont/blob/master/Assets/EFIconFont.png?raw=true)

<p align="center">
    <a href="https://travis-ci.org/EFPrefix/EFIconFont">
    	<img src="https://api.travis-ci.org/EFPrefix/EFIconFont.svg?branch=master">
    </a>
    <a href="http://cocoapods.org/pods/EFIconFont">
    	<img src="https://img.shields.io/cocoapods/v/EFIconFont.svg?style=flat">
    </a>
    <a href="http://cocoapods.org/pods/EFIconFont">
    	<img src="https://img.shields.io/cocoapods/p/EFIconFont.svg?style=flat">
    </a>
    <a href="https://github.com/apple/swift">
    	<img src="https://img.shields.io/badge/language-swift-orange.svg">
    </a>
    <a href="https://codebeat.co/projects/github-com-efprefix-eficonfont-master">
        <img src="https://codebeat.co/badges/4cbadc4d-e8f9-4f5b-8ee5-676ba6380383" />
    </a>
    <a href="https://raw.githubusercontent.com/EFPrefix/EFIconFont/master/LICENSE">
    	<img src="https://img.shields.io/cocoapods/l/EFIconFont.svg?style=flat">
    </a>
    <a href="https://twitter.com/EyreFree777">
    	<img src="https://img.shields.io/badge/twitter-@EyreFree777-blue.svg?style=flat">
    </a>
    <a href="http://weibo.com/eyrefree777">
    	<img src="https://img.shields.io/badge/weibo-@EyreFree-red.svg?style=flat">
    </a>
    <img src="https://img.shields.io/badge/made%20with-%3C3-orange.svg">
</p>

A ordinary icon font package helps you to use icon font more easily in your project.

> [中文介绍](https://github.com/EFPrefix/EFIconFont/blob/master/README_CN.md)

## Preview

| 1  | 2 | 3 |
|:-:|:-:|:-:|
| ![](https://github.com/EFPrefix/EFIconFont/blob/master/Assets/1.png?raw=true) | ![](https://github.com/EFPrefix/EFIconFont/blob/master/Assets/2.png?raw=true) | ![](https://github.com/EFPrefix/EFIconFont/blob/master/Assets/3.png?raw=true) |

## Example

To run the example project manually, clone the repo, demo is in the 'Example' folder, then open `EFIconFont.xcworkspace` with Xcode and select the target you want, run.

Or you can run the following command in terminal:

```bash
git clone git@github.com:EFPrefix/EFIconFont.git; cd EFIconFont/Example; pod install; open EFIconFont.xcworkspace
```

## Requirements

- iOS 8.0+
- Swift 4.2+

## Installation

EFIconFont is available through [CocoaPods](https://cocoapods.org). To install it, simply add the following line to your Podfile:

```ruby
pod 'EFIconFont'
```

You can get iconfonts of `AntDesign` and `FontAwesome` by the following way:

```ruby
pod 'EFIconFont', :subspecs => ['Core', 'AntDesign', 'FontAwesome']
```

Then, run the following command:

```bash
pod install
```

## Use

### 1. Core

Objects that implement the `EFIconFontProtocol` protocol can transform themselves into `NSAttributedString` or `UIImage`, which is as follows:

```swift
public protocol EFIconFontProtocol {

    // `name` is not necessarily equal to .ttf file name
    var name: String { get }

    // `path` is path of .ttf file
    var path: String { get }

    // `unicode` is unique identifier of particular icon
    var unicode: String { get }

    // `attributes` is style of icon
    var attributes: [NSAttributedString.Key : Any] { set get }
}
```

- name: Font name, not necessarily equal to .ttf file name, you can use [BirdFont](https://birdfont.org) to see the `Name` attribute of the file;
- path: Filepath of `.ttf` file;
- unicode: The unique unicode of an icon;
- attributes: Default attributes of icon.

Objects that implement the protocol can be converted to strings and images by calling the following methods, you can also change the foreground color and size:

```swift
// MARK:- String
func attributedString(size fontSize: CGFloat, attributes: [NSAttributedString.Key : Any]?) -> NSAttributedString?
func attributedString(size fontSize: CGFloat, foregroundColor: UIColor? = nil, backgroundColor: UIColor? = nil) -> NSAttributedString?

// MARK:- Image
func image(size fontSize: CGFloat, attributes: [NSAttributedString.Key : Any]?) -> UIImage?
func image(size fontSize: CGFloat, foregroundColor: UIColor? = nil, backgroundColor: UIColor? = nil) -> UIImage?
func image(size imageSize: CGSize, attributes: [NSAttributedString.Key : Any]?) -> UIImage?
func image(size imageSize: CGSize, foregroundColor: UIColor? = nil, backgroundColor: UIColor? = nil) -> UIImage?
```

### 2. Extend

This pod has integrated the free resources of `AntDesign` and `FontAwesome` in the subspecs of AntDesign and FontAwesome. It can be imported by who need to use it. The usage methods are as follows:

```swift
EFIconFontAntDesign.addteam.attributedString(size: 24)
EFIconFontFontAwesomeBrands.adobe.attributedString(size: 32, foregroundColor: UIColor.white, backgroundColor: UIColor.green)
EFIconFontFontAwesomeRegular.addressBook.image(size: 24, foregroundColor: UIColor.red)
EFIconFontFontAwesomeSolid.alignLeft.image(size: CGSize(width: 36, height: 48), foregroundColor: UIColor.white)
```

PS: Please make sure that your usage follows the original author's license.

### 3. Other

Use and code generation of some icon font resource sites:

- [iconfont.cn](https://github.com/EFPrefix/EFIconFont/blob/master/Extend/iconfont.md)
- [fontawesome.com](https://github.com/EFPrefix/EFIconFont/blob/master/Extend/fontawesome.md)

## Packs

| Name | Version | Count | File Size | Description | License | Preview |
|:-|:-|:-|:-|:-|:-|:-|
| AntDesign | | 557 | 127KB | Ant Design | [MIT](https://github.com/ant-design/ant-design/blob/master/LICENSE) | [iconfont.cn](https://www.iconfont.cn/collections/detail?cid=9402) |
| ElusiveIcons | 2.0.0 | 304 | 53KB | Elusive Icons | [OFL](http://elusiveicons.com/license/) | [elusiveicons.com/](http://elusiveicons.com/icons/) |
| FontAwesome | 5.8.1 | 1516 | 356KB | Font Awesome | [Font Awesome Free License](https://fontawesome.com/license/free) | [fontawesome.com](https://fontawesome.com/icons?d=gallery&m=free) |
| Ionicons | 4.5.5 | 696 | 143KB | Ionicons | [MIT](https://github.com/ionic-team/ionicons/blob/master/LICENSE) | [ionicons.com](https://ionicons.com/) |
| Octicons | 8.4.2 | 184 | 34KB | GitHub's icons | [GitHub Logos and Usage](https://github.com/logos) | [octicons.github.com](https://octicons.github.com/) |

## Author

EyreFree, eyrefree@eyrefree.org

## License

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/License_icon-mit-88x31-2.svg/128px-License_icon-mit-88x31-2.svg.png">

EFIconFont is available under the MIT license. See the [LICENSE](LICENSE) file for more info.
