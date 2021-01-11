
[![](https://cf-assets2.tenlong.com.tw/products/images/000/154/714/webp/9789864344789_bc.webp?1606208192)](https://www.tenlong.com.tw/products/9789864344789)

1. 介紹什麼叫做 Declarative 
2. (基本元件) Text
3. (基本元件) Image
4. (基本元件) VStack, HStack, ZStack
5. (基本元件) ScrollView
6. (基本元件) Button, Label, Gradient
7. @State, @Binding
8. 路徑 + 形狀，以圓餅圖為例子
9. 動畫 + 轉場，以下載進度指示器為例子
10. List + ForEach，建立表單
11. NavigationView 
12. AlertView
13. Picker + Stepper = Form
14. Combine + Environment
15. Combine + RegisterForm
16. tableView delegate & edit
17. Gesture
18. Gesture + GeometryReader
19. 仿 Tinder 滑動卡片手勢與動畫效果
20. 仿 Wallet 滑動卡片手勢與動畫效果
21. JSON + Slider = DataFilter


- SwiftUI 中，Color 也是一種視圖 (p.40)
- .frame(minWidth: 0, maxWidth: .infinity) 可以設定視圖大小約束 (p.54)
- 水平方向若有兩個 .infinity 則會等寬分佈 (p.55)
- modifier 是有順序性的，例如「padding 放在 background 之後」與倒序則會有不同的效果 (p.91)
- @Binding 可做為依賴另一個變數的狀態屬性，且該變數可雙向 get/set 該屬性 (p.115)
- 「自訂返回按鈕」 (p.188)
- 用戶與程式互動的狀況可以使用時間軸表示，每一個互動產生的事件都是在軸上的一個值。Reactive 的精神在於處理這些值，當然 Combine 也是 (p.253)
- Combine 的使用範例，以監聽 textField 事件為例子說明「如何處理 streaming event」 (p.254)

### 自定義形狀
![](./Screen%20Shot%20SwiftUI%20shape.png?raw=true)
```swift
struct DemoShape: Shape {
    func path(in rect: CGRect) -> Path {
        var path = Path()
        let topL = CGPoint(x: rect.minX, y: rect.minY)
        let topR = CGPoint(x: rect.maxX, y: rect.minY)
        path.move(to: topL)
        path.addQuadCurve(to: topR, control: CGPoint(x: rect.width/2, y: -(rect.width*0.1)))
        path.addRect(CGRect(origin: topL, size: rect.size))
        return path
    }
}
```
對某一個 View 套用即可呈現我們自定義的形狀
```swift
Text("測試說明文字")
  .background(
    DemoShape()
      .fill(Color.red)
  )
```
