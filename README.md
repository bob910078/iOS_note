# iOS_note

| sign | description |
|------|-------------|
|     | 蘋果官方 |
|  📼  | WWDC video |
|  📝  | article |
|  💾  | sample code |


## 需要研讀的：
- 理解和分析 app 的崩潰報告 [📝 Understanding and Analyzing Application Crash Reports](https://developer.apple.com/library/archive/technotes/tn2151/_index.html)


## 覺得有趣的議題：
- 選中狀態的 cell 樣式改變 [💾 Changing the Appearance of Selected and Highlighted Cells](https://developer.apple.com/documentation/uikit/uicollectionviewdelegate/changing_the_appearance_of_selected_and_highlighted_cells)
- 使用手勢來做多選項目 [💾 Selecting Multiple Items with a Two-Finger Pan Gesture](https://developer.apple.com/documentation/uikit/uitableviewdelegate/selecting_multiple_items_with_a_two-finger_pan_gesture)
- 可以客製化的輸入操作介面 [📝 Custom Keyboard App Extension Programming Guide](https://developer.apple.com/library/archive/documentation/General/Conceptual/ExtensibilityPG/CustomKeyboard.html#//apple_ref/doc/uid/TP40014214-CH16-SW1)


## `UITableView` 的自學之路：
號稱八成以上的 app 都在使用的 UI 神器
- 認識一下官方對他的用途說明 [link](https://developer.apple.com/documentat\ion/uikit/views_and_controls/table_views#//apple_ref/doc/uid/TP40007451)
- [Table View Programming Guide for iOS](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/TableView_iPhone/TableViewAPIOverview/TableViewAPIOverview.html#//apple_ref/doc/uid/TP40007451-CH4-SW2)
- [Creating and Configuring a Table View](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/TableView_iPhone/CreateConfigureTableView/CreateConfigureTableView.html)

### 跟 UICollectionView 尬作伙
- [Collection View Programming Guide for iOS](https://developer.apple.com/library/archive/documentation/WindowsViews/Conceptual/CollectionViewPGforIOS/Introduction/Introduction.html)


## 文字系列的自學之路：
- [Text System User Interface Layer Programming Guide](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/TextUILayer/TextUILayer.html#//apple_ref/doc/uid/10000090-SW1)
- [Cocoa Text Architecture Guide](https://developer.apple.com/library/archive/documentation/TextFonts/Conceptual/CocoaTextArchitecture/Introduction/Introduction.html#//apple_ref/doc/uid/TP40009459)
- [Managing Text Fields and Text Views](https://developer.apple.com/library/archive/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/ManageTextFieldTextViews/ManageTextFieldTextViews.html#//apple_ref/doc/uid/TP40009542-CH10-SW1)
- [Custom Views for Data Input](https://developer.apple.com/library/archive/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/InputViews/InputViews.html#//apple_ref/doc/uid/TP40009542-CH12)
- [Core Text Tutorial for iOS: Making a Magazine App](https://www.raywenderlich.com/578-core-text-tutorial-for-ios-making-a-magazine-app)
- [String Programming Guide / Words, Paragraphs, and Line Breaks](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/Strings/Articles/stringsParagraphBreaks.html#//apple_ref/doc/uid/TP40005016-SW1)
  - Unicode defines:
    - an unambiguous paragraph separator, U+2029 (for which Cocoa provides the constant NSParagraphSeparatorCharacter), 
    - an unambiguous line separator, U+2028 (for which Cocoa provides the constant NSLineSeparatorCharacter).
  - Some older Macintosh software recognizes only `\r`, and some Windows software recognizes only `\r\n`.
- [Text Programming Guide for iOS / Using Text Kit to Draw and Manage Text](https://developer.apple.com/library/archive/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/CustomTextProcessing/CustomTextProcessing.html)
- [Text Layout Programming Guide / Calculating Text Height](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/TextLayout/Tasks/StringHeight.html#//apple_ref/doc/uid/20001809-CJBGBIBB)



## iOS app 的設計理念
- [View Controllers and Navigation-Based Apps](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/TableView_iPhone/TableViewAndDataModel/TableViewAndDataModel.html#//apple_ref/doc/uid/TP40007451-CH5-SW7)
- [Auto Layout Guide: Views with Intrinsic Content Size](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/AutolayoutPG/ViewswithIntrinsicContentSize.html)
- [Auto Layout Guide: Working with Scroll Views](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/AutolayoutPG/WorkingwithScrollViews.html#//apple_ref/doc/uid/TP40010853-CH24-SW1)
- [View and Window Architecture](https://developer.apple.com/library/archive/documentation/WindowsViews/Conceptual/ViewPG_iPhoneOS/WindowsandViews/WindowsandViews.html#//apple_ref/doc/uid/TP40009503-CH2-SW1)
- [Determine Why Your App Launched](https://developer.apple.com/documentation/uikit/app_and_environment/responding_to_the_launch_of_your_app#2922740)
- [💾 UIKit Catalog: Creating and Customizing Views and Controls](https://developer.apple.com/documentation/uikit/views_and_controls/uikit_catalog_creating_and_customizing_views_and_controls)
- [💾 Autosizing Views for Localization in iOS](https://developer.apple.com/documentation/xcode/autosizing_views_for_localization_in_ios)
- [Cocoa Core Competencies](https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/ControllerObject.html) （蘋果官方解釋MVC的文件！！！）
- [View Controller Programming Guide for iOS (Legacy)](https://developer.apple.com/library/archive/documentation/WindowsViews/Conceptual/ViewControllerPGforiOSLegacy/BasicViewControllers/BasicViewControllers.html#//apple_ref/doc/uid/TP40011381-CH101-SW1)
- [View Controller Programming Guide for iOS](https://developer.apple.com/library/archive/featuredarticles/ViewControllerPGforiPhoneOS/index.html#//apple_ref/doc/uid/TP40007457)


## iOS app 渲染畫面概念

- [Drawing and Printing Guide for iOS / iOS Drawing Concepts](https://developer.apple.com/library/archive/documentation/2DDrawing/Conceptual/DrawingPrintingiOS/GraphicsDrawingOverview/GraphicsDrawingOverview.html#//apple_ref/doc/uid/TP40010156-CH14-SW3)
- UIGraphicsBeginImageContextWithOptions



劉奶奶進大觀園：
- isBaselineRelativeArrangement
- requiresConstraintBasedLayout
- layoutFittingExpandedSize
- showingDeleteConfirmation
- preservesSuperviewLayoutMargins
- systemLayoutSizeFitting
- NSUserActivity




## Homebrew 

- brew install {package name}
- brew uninstall {package name}
- brew info {package name}
- brew search {package name}
- brew list // 列出已安裝的套件
- brew outdated // 列出可更新的套件
- brew upgrade // 更新可更新的套件
- brew update // 更新 homebrew
