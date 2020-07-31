# 研究 keyboard 彈出與收起的通知

透過 [附錄一](https://github.com/bob910078/iOS_note/new/master#附錄一) 的範例 code 可以知道鍵盤的順序。

## 鍵盤彈出 事件順序
1. UIKeyboardWillChangeFrameNotification
2. UIKeyboardWillShowNotification
3. UIKeyboardDidChangeFrameNotification
4. UIKeyboardDidShowNotification

## 鍵盤收起 事件順序
1. UIKeyboardWillChangeFrameNotification
2. UIKeyboardWillHideNotification
3. UIKeyboardDidChangeFrameNotification
4. UIKeyboardDidHideNotification
 
## 鍵盤動畫數值
- UIKeyboardAnimationDurationUserInfoKey = 0.25
- UIKeyboardAnimationCurveUserInfoKey = 7  (AnimationCurve.easeInOut)
- UIKeyboardIsLocalUserInfoKey = 1  (鍵盤是否顯示)

## 推薦學習資源：
- [ Text Programming Guide for iOS - Managing the Keyboard](https://developer.apple.com/library/archive/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/KeyboardManagement/KeyboardManagement.html)
- [iOS 推鍵盤的大小事 - 1](https://medium.com/@yolk/ios-推鍵盤的大小事-1-90c482396f7d)



## 附錄一

```swift 

override func viewDidLoad() {
    super.viewDidLoad()
    // Do any additional setup after loading the view.
    
    let nc = NotificationCenter.default
    
    // Show
    nc.addObserver(self, selector: #selector(keyboardWS(_:)), name: UIResponder.keyboardWillShowNotification, object: nil)
    nc.addObserver(self, selector: #selector(keyboardDS(_:)), name: UIResponder.keyboardDidShowNotification, object: nil)
    
    // Hide
    nc.addObserver(self, selector: #selector(keyboardWH(_:)), name: UIResponder.keyboardWillHideNotification, object: nil)
    nc.addObserver(self, selector: #selector(keyboardDH(_:)), name: UIResponder.keyboardDidHideNotification, object: nil)
    
    // Frame Change
    nc.addObserver(self, selector: #selector(keyboardWF(_:)), name: UIResponder.keyboardWillChangeFrameNotification, object: nil)
    nc.addObserver(self, selector: #selector(keyboardDF(_:)), name: UIResponder.keyboardDidChangeFrameNotification, object: nil)
}

@objc func keyboardWS(_ notification: Notification) {
    print(notification)
}
@objc func keyboardDS(_ notification: Notification) {
    print(notification)
}

@objc func keyboardWH(_ notification: Notification) {
    print(notification)
}
@objc func keyboardDH(_ notification: Notification) {
    print(notification)
}

@objc func keyboardWF(_ notification: Notification) {
    print(notification)
}
@objc func keyboardDF(_ notification: Notification) {
    print(notification)
}

```


## 附錄二

以下為節錄 iPhone SE2 在 portrait（手機直立）的鍵盤彈出 `Notification` 物件資訊：

```
name = UIKeyboardWillChangeFrameNotification, 
object = nil, 
userInfo = Optional(
[
  AnyHashable("UIKeyboardBoundsUserInfoKey"): NSRect: {{0, 0}, {375, 260}}, 
  AnyHashable("UIKeyboardFrameEndUserInfoKey"): NSRect: {{0, 407}, {375, 260}}, 
  AnyHashable("UIKeyboardCenterEndUserInfoKey"): NSPoint: {187.5, 537}, 
  AnyHashable("UIKeyboardIsLocalUserInfoKey"): 1, 
  AnyHashable("UIKeyboardFrameBeginUserInfoKey"): NSRect: {{0, 667}, {375, 260}}, 
  AnyHashable("UIKeyboardAnimationDurationUserInfoKey"): 0.25, 
  AnyHashable("UIKeyboardAnimationCurveUserInfoKey"): 7, 
  AnyHashable("UIKeyboardCenterBeginUserInfoKey"): NSPoint: {187.5, 797}
])
```


