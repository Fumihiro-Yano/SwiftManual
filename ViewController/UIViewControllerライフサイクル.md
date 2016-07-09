## UIViewControllerライフサイクル

### ライフサイクルの挙動
```
override func viewDidLoad() {
 super.viewDidLoad()
 println("ViewController/viewDidLoad/インスタンス化された直後（初回に一度のみ）")

}

override func viewWillAppear(animated: Bool) {
 super.viewDidDisappear(animated)
 println("ViewController/viewWillAppear/画面が表示される直前")
}

override func viewDidAppear(animated: Bool) {
 super.viewDidAppear(animated)
 println("ViewController/viewDidAppear/画面が表示された直後")
}

override func viewWillDisappear(animated: Bool) {
 super.viewWillDisappear(animated)
 println("ViewController/viewWillDisappear/別の画面に遷移する直前")
}

override func viewDidDisappear(animated: Bool) {
 super.viewDidDisappear(animated)
 println("ViewController/viewDidDisappear/別の画面に遷移した直後")
}
```

### タブバーでの挙動
```
init(インスタンス作成時に呼び出したイニシャライザ)
↓
viewDidLoad
・View が初めて呼び出される時に1回だけ呼ばれます。
・アプリ起動後に初めて当Viewが表示された場合に1度だけ呼ばれます。
↓
viewWillAppear
・View が表示される直前に呼ばれるメソッド
・タブ等の切り替え等により、画面に表示されるたびに呼び出されます。
・タブが切り替わるたびに何度でも呼ばれます。
↓
viewDidAppear
・View の表示が完了後に呼び出されるメッソド
・タブ等の切り替え等により、画面に表示されるたびに呼び出されます。
・タブが切り替わるたびに何度でも呼ばれます。
↓
viewWillDisappear
・View が他のView (画面から消える) 直前に呼び出されるメッソド
・View が他のView (画面から消える) 直前に呼び出されるメッソド
・タブが切り替わるたびに何度でも呼ばれます。
↓
viewDidDisappear
・View が他のView (画面から消えた) 非表示後に呼び出されるメッソド
・View が他のView (画面から消える) 直前に呼び出されるメッソド
・タブが切り替わるたびに何度でも呼ばれます。
```

[参考1](http://blog.77jp.net/iphone%E9%96%8B%E7%99%BA-uiviewcontroller-%E3%83%A9%E3%82%A4%E3%83%95%E3%82%B5%E3%82%A4%E3%82%AF%E3%83%AB-viewdidload-viewwillappear-viewdidappear-viewwilldisappear-viewdiddisappear-ios-%E9%80%86)

[参考2](http://qiita.com/kayo_h/items/4710c4ac02a191652a96)
