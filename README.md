经过三代的更迭，最新版本的 Kongzue DialogX 已经到来，不仅仅保留了以往的优势，更带来了更灵活的扩展性和全新的流畅体验。

<a href="https://github.com/kongzue/dialogX/">
<img src="https://img.shields.io/badge/Kongzue%20Dialog-Alpha-green.svg" alt="Kongzue Dialog">
</a> 
<a href="https://bintray.com/myzchh/maven/dialogx/0.0.1/link">
<img src="https://img.shields.io/badge/Maven-Alpha-blue.svg" alt="Maven">
</a> 
<a href="http://www.apache.org/licenses/LICENSE-2.0">
<img src="https://img.shields.io/badge/License-Apache%202.0-red.svg" alt="License">
</a> 
<a href="http://www.kongzue.com">
<img src="https://img.shields.io/badge/Homepage-Kongzue.com-brightgreen.svg" alt="Homepage">
</a>

# DialogX优势

- DialogX 采用全新的实现方式，**不**依赖 AlertDialog、Window 或 Fragment 实现，更加轻便快捷。
- DialogX 的启动无需 context 参数，默认提供静态方法一句代码实现对话框的启动，使用更加方便。
- DialogX 采用分离设计，默认自带 Material 主题，可选引入 IOS、Kongzue 等其他风格主题，大大减小 App 体积，同时提供了主题接口，如有定制需求完全可以自行实现一套私有主题。
- 更低的耦合度，更少的问题，例如 DialogX 可以在对话框正在运行的过程中随意关闭 Activity ，而无需担心引发 WindowLeaked 错误。
- 更流畅的体验，DialogX 的动画效果更加丰富，对话框启动动画采用非线性动画实现，更自带连贯的等待提示到完成错误动画过渡效果，让你的 APP 更具动感。
- 所有主题默认支持亮暗色两种模式，只需一键配置即可实现亮暗色的对话框主题切换，更有自由的布局内容满足定制化需求。
- 轻松的实现对话框的生命周期管控以及沉浸式适配。

# DialogX对话框

DialogX 包含以下对话框组件：

- 基础对话框 MessageDialog和 输入对话框 InputDialog

  ![基础对话框 MessageDialog和 输入对话框 InputDialog](https://github.com/kongzue/DialogX/raw/master/readme/messagedialog.png)

  基础对话框组件可以实现基本的对话框业务逻辑，包含标题、消息文本、单/双/三按钮的提醒功能，三个按钮可以按照纵向/横向进行显示，满足绝大部分日常阻断式提醒需求。

  输入对话框 InputDialog 是基础对话框的扩展组件，除了包含基础的功能外还提供了输入框，可自定义输入提示文本、输入文字样式和点击按钮后的输入内容回调等。

- 等待框 WaitDialog 和提示框 TipDialog

  ![等待框 WaitDialog 和提示框 TipDialog](https://github.com/kongzue/DialogX/raw/master/readme/waitdialog.png)

  阻断式等待提示框，会显示基础的环形等待动画以及进度展示动画，它是单例的，这就意味着从等待状态 WaitDialog 切换到提示状态 TipDialog 是无缝的，你可以自由的选择在等待结束后显示成功/警告/错误三种状态的消息提示，动画的切换也会无缝衔接。

- 底部对话框 BottomDialog 和底部菜单 BottomMenu

  ![底部对话框 BottomDialog 和底部菜单 BottomMenu](https://github.com/kongzue/DialogX/raw/master/readme/bottomdialog.png)

  底部对话框 BottomDialog 提供从底部弹出显示的对话框样式，可设置标题、提示文本和自定义布局，使用 Material 主题时还会提供向下滑动关闭和向上滑动展开的功能。

  底部菜单 BottomMenu 则是底部对话框 BottomDialog 的扩展组件，在底部对话框的基础上额外提供了菜单功能，菜单可设置菜单内容/菜单图标/单选功能，在不同的主题下还可以提供“取消”关闭按钮（注：因 Material 直接可以下滑关闭因此 Material 主题不提供额外的“取消”关闭按钮）

- 简单提示 PopTip

  ![简单提示 PopTip](https://github.com/kongzue/DialogX/raw/master/readme/poptip.png)

  提供一个类似 Toast 的文本提示功能，但它拥有更强大的自定义属性。你可以设置文本提示、图标、以及一个控制按钮，并可以设置持续显示或定义自动消失的时长。PopTip 是非阻断式提示，也就是说，在 PopTip 显示时用户依然可以操作界面。

- 全屏对话框 FullScreenDialog

  ![全屏对话框 FullScreenDialog](https://github.com/kongzue/DialogX/raw/master/readme/fullscreendialog.png)

  全屏对话框 FullScreenDialog 提供从底部弹出的对话框效果，类似 BottomDialog 但相比 BottomDialog 的定制化自由度更高。全屏对话框 FullScreenDialog 将不提供任何基础实现，开发者可以自定义实现布局。默认只提供一个默认的下划关闭逻辑和 Activity 背景下沉的显示效果。

- 自定义对话框 CustomDialog

  ![自定义对话框 CustomDialog](https://github.com/kongzue/DialogX/raw/master/readme/customdialog.png)

  根据定制化自由度的对话框组件，完全由用户自行实现布局内容。CustomDialog 提供了 ALIGN 选项可以轻松定制对话框弹出的方式，默认支持屏幕中央、屏幕底部和屏幕顶部三种弹出模式，也会提供相应的弹出动画效果，当然用户也可以自定义动画效果。

# DialogX主题

![DialogX主题](https://github.com/kongzue/DialogX/raw/master/readme/allstyle.png)

DialogX 采用了主体分离结构，主框架仅包含 Material 设计风格的对话框组件，您可以通过额外引入主题包来实现主题的扩展。

额外的，每套主题都包含亮色/暗色两种显示风格，您可以通过 DialogX 的设置自由切换对话框的显示效果。

主题设计开发者也可以通过使用 DialogX 提供的主题定制接口来实现自定义主题，或者对现有主题进行样式调整和修改。

# 开始使用DialogX

因为依赖的关系，DialogX 目前仅支持 AndroidX 作为基础进行开发，若您正在使用最新版本的 Android Studio，那么默认创建的项目就是使用 AndroidX 作为底层框架的，老版本 Android Support 兼容库将在后续更新。

想要在您的项目引入 DialogX，您需要在 app 的 build.gradle 文件中找到 `dependencies{}` 代码块，并在其中加入以下语句：

```
implementation 'com.kongzue.dialogx:DialogX:0.0.1'
```

若有需要，也可以手动配置 Maven：

```xml
<dependency>
  <groupId>com.kongzue.dialogx</groupId>
  <artifactId>DialogX</artifactId>
  <version>0.0.1</version>
  <type>pom</type>
</dependency>
```

具体的使用说明，请参阅 [DialogX Wiki](https://github.com/kongzue/DialogX/wiki/%E6%AC%A2%E8%BF%8E%E4%BD%BF%E7%94%A8-DialogX)

# 开源协议

DialogX 遵循 Apache License 2.0 开源协议。

```
Copyright Kongzue DialogX

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

 http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```