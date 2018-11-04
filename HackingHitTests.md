# Hacking Hit Tests

让我们回到 [Crusty 教我们面向协议编程](https://developer.apple.com/videos/play/wwdc2015/408/) 之前的日子，共享实现主要是通过继承来完成的。在和 UIKit 编程打交道的每一天，你可以创建一个 `UIView` 的子类，增加一些子视图，覆盖 `-layoutSubviews` 方法，然后重复这个过程。你可能会覆盖 `-drawRect` 方法。但在奇怪的日子里，当你需要做一些奇怪的事时，你开始考虑那些在 `UIView` 中你可以覆盖的其他方法。

UIKit 更古怪的部分之一是触摸处理子系统。这主要包括了两个方法: `-pointInside:withEvent: ` 和 `-hitTest:withEvent:`。

`-pointInside:` 告诉调用者给与的一个点是否在一个