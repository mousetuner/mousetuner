<img src="docs/icon.png" width="88" alt="MouseTuner">

# MouseTuner

[English](README.md) · [简体中文](README.zh-CN.md)

给 macOS 上的鼠标补齐系统没有给的那部分体验，常驻菜单栏。

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/scroll-dark.webp">
  <img alt="滚动面板，可以看到 Scroll Curve、参数滑块与实时预览" src="docs/shots/scroll-light.webp">
</picture>

滚动面板：Scroll Curve、它的五个参数，以及拖动时实时跟着变的预览。

## 它做什么

- **平滑滚动。** 把滚轮的离散跳动换成像素级的惯性滚动。触控板与妙控鼠标原样通过，不受影响。
- **滚动方向反转。** 单独翻转滚轮方向，不受系统「自然滚动」牵连，鼠标和触控板不必再保持一致。
- **滚动曲线编辑器。** 调最小步长、速度增益、时长与衰减，拖动的同时就能感觉到变化。
- **按键映射。** 触发可以是单击、双击、长按、四方向拖拽、两键同按，或者按住某键再滚动。动作可以是发送快捷键、执行系统动作、打开应用或网址，也可以运行脚本。
- **修饰键按住。** 按住鼠标键就等于按住 Fn 这类修饰键，松开即松开。按住说话的语音输入，硬件这一半就是它。
- **按住拖动画布。** 按住某键期间把指针位移换算成滚动，像地图或画布里的抓手工具。
- **按应用覆盖。** 滚动曲线与按键映射可以随前台应用变化。
- **输入法自动切换。** 按应用切换，或者按浏览器当前标签页的域名切换。
- **罗技硬件控制。** 在已识别的设备上，经 HID++ 读写 DPI、SmartShift 与电量。HID++ 就是厂商自家软件说的那套协议，用它不需要厂商软件在后台运行。

平滑滚动与按键映射对任何鼠标都生效。硬件控制需要 MouseTuner 认得出的设备。

## 界面

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/buttons-dark.webp">
  <img alt="按键映射面板，可以看到触发与它们对应的动作" src="docs/shots/buttons-light.webp">
</picture>

按键映射：一个按键挂一串触发，每个触发只指向一个动作。两者都可以按应用覆盖。

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/device-dark.webp">
  <img alt="设备面板，可以看到已识别鼠标的 DPI、SmartShift 与电量" src="docs/shots/device-light.webp">
</picture>

设备：在 MouseTuner 认得出的鼠标上，经 HID++ 读写 DPI、SmartShift 与电量。

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/inputsource-dark.webp">
  <img alt="输入法面板，可以看到按应用与按域名的规则" src="docs/shots/inputsource-light.webp">
</picture>

输入法：按应用切换，或者按浏览器当前标签页的域名切换。

截图取自英文界面，应用本身有八种语言。

## 系统要求

macOS 13.3 及以上。通用二进制，Apple 芯片与 Intel 都支持。

## 安装

下载 [MouseTuner.dmg](https://github.com/mousetuner/mousetuner/releases/latest/download/MouseTuner.dmg)——Developer ID 签名并经过公证，不到 4 MB——或者用 Homebrew：

```
brew install --cask mousetuner/tap/mousetuner
```

首次启动会要辅助功能权限。滚动与按键映射都靠拦截系统输入事件，没有这个权限它们无法工作。**不需要**输入监控权限。

## 价格

$9.9 买断，国内 ¥68。不是订阅。

一把 key 可以激活 3 台机器，终身免费更新。买之前有 30 天全功能试用，不需要账号，也不需要填付款方式。14 天无理由退款。

## 隐私

无账号，不做统计，不含崩溃上报组件。

应用自身只发四条网络请求：首次启动登记试用、激活、每天一次吊销校验、停用。请求体里只有 license key 的哈希与机器指纹哈希——没有账号，也没有任何关于你怎么用这个应用的信息。完整清单连同每条的触发条件与请求体发布在 [mousetuner.com/privacy](https://mousetuner.com/privacy)，可以拿抓包逐条核对。

## 与 Logi Options+ 的关系

大多数人装 Options+ 是为了那几样硬件控制——DPI、SmartShift、电量、拇指键——这些 MouseTuner 都有，另外还多了平滑滚动与按应用覆盖，那两样 Options+ 不做。它也能用在非罗技鼠标上，而 Options+ 结构上做不到。

它**不**替代 Flow（一套鼠标控制多台电脑）、固件更新、罗技键盘，以及 Actions Ring。这几样里只要有一样你离不开，就留着 Options+，两者可以同时装。

逐项对照见 [mousetuner.com/logi-options-plus-alternative](https://mousetuner.com/logi-options-plus-alternative)

## 支持的鼠标

平滑滚动与按键映射对**任何**鼠标都生效，只有 HID++ 硬件控制才需要已识别的机型。

目前列了 16 款罗技机型（MX Master、MX Anywhere、MX Ergo、MX Vertical、M720 等）。型号名与 PID 取自 libratbag，也就是 Linux 那边的开源设备数据库——它能证明某个设备说 HID++，但证明不了它支持哪些能力，所以每一行都标着**已识别，硬件控制尚未验证**。要验证就得有实机采集数据；如果你手上正好有其中一款，提交一份采集记录是最有用的贡献。

当前名单：[mousetuner.com/compatibility](https://mousetuner.com/compatibility)

## 链接

- 官网：[mousetuner.com](https://mousetuner.com)
- 文档——每一种 Trigger 与 Action、各个设置面板、术语表：[mousetuner.com/docs](https://mousetuner.com/docs)
- 更新日志：[mousetuner.com/changelog](https://mousetuner.com/changelog)
- 报 bug 与提交设备采集记录：[Issues](https://github.com/mousetuner/mousetuner/issues)

应用界面有八种语言：英语、简体中文、繁体中文、日语、韩语、德语、法语、西班牙语。
