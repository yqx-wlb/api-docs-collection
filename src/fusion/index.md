# Fusion Design 组件文档汇总


## affix

# zh-CN order=4

# 启用绝对布局

可以通过 `container` 属性设置 Affix 组件需要监听其滚动事件的元素，该属性接收一个函数作为参数，默认为 `() => window`；
设置 useAbsolute 为 true，通过 absolute 布局实现组件固定。

# en-US order=4

# Container

Change the default container by passing a function to `container`;
enable `useAbsolute` to use `absolute position` to implement affix component;


---


## affix

# zh-CN order=0

# 基本

默认情况下，Affix 的默认目标容器元素是整个 `window`，并且 `offsetTop = 0`，
也就意味着当页面往下滚动时，当 Affix 元素接触到浏览器边框时，此时会将 Affix 钉住。

# en-US order=0

# Basic

The simple usage is to wrap your components direcly with Affix component.


---


## affix

# zh-CN order=3

# 自定义目标容器

可以通过 `container` 属性设置 Affix 组件需要监听其滚动事件的元素，该属性接收一个函数作为参数，默认为 `() => window`。

# en-US order=3

# Container

Change the default container by passing a function to `container`.


---


## affix

# zh-CN order=2

# 自定义偏移量

可以通过 `offsetTop` 或 `offsetBottom` 自定义偏移量。

# en-US order=2

# Offset

Setting the offset by `offsetTop` or `offsetBottom`.


---


## affix

# zh-CN order=1

# 固钉事件

`onAffix` 该函数会在状态变化时返回固钉状态。向下滚动查看效果

# en-US order=1

# onAffix

Listening the affix state by `onAffix`.


---


## affix

# Affix

-   category: Components
-   family: Util
-   chinese: 固钉
-   type: 基本

---

将页面元素钉在可视范围。

## 何时使用

-   当内容区域比较长，需要滚动页面时，这部分内容对应的操作或者导航需要在滚动范围内始终展现。常用于侧边菜单和按钮组合。
-   页面可视范围过小时，慎用此功能以免遮挡页面内容。

## API

### Affix

| 参数         | 说明                                                                                                  | 类型                       | 默认值        | 是否必填 |
| ------------ | ----------------------------------------------------------------------------------------------------- | -------------------------- | ------------- | -------- |
| container    | 设置 Affix 需要监听滚动事件的容器元素<br/><br/>**签名**:<br/>**返回值**:<br/>目标容器元素             | () => Element \| Window    | () =\> window |          |
| offsetTop    | 距离窗口顶部达到指定偏移量后触发                                                                      | number                     | -             |          |
| offsetBottom | 距离窗口底部达到指定偏移量后触发                                                                      | number                     | -             |          |
| onAffix      | 当元素的样式发生固钉样式变化时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_affixed_: 是否固定 | (affixed: boolean) => void | -             |          |
| useAbsolute  | 是否启用绝对布局实现 affix                                                                            | boolean                    | -             |          |
| className    | 包裹 children 容器的类名                                                                              | string                     | -             |          |
| style        | 最外层容器的 style 样式                                                                               | React.CSSProperties        | -             |          |


---


## animate

# zh-CN order=0

# 基本

展示单个子元素的进场离场动画。

# en-US order=0

# Basic

Demo the enter and leave animation of a child element.


---


## animate

# zh-CN order=2

# 展开收起动画

展示单个子元素的展开收起动画。

# en-US order=2

# Expand and collapse animation

Demo the expand and collapse animation of a child element.


---


## animate

# zh-CN order=1

# 多个子元素动画

展示多个子元素的进场离场动画。

# en-US order=1

# Multiple child elements animation

Demo the enter and leave animation of multiple child elements.


---


## animate

# Animate

-   category: Utility
-   family: Util
-   chinese: 动画

---

动画组件。

## 何时使用

为组件增加自定义动画效果。

## API

### Animate

| 参数            | 说明                                                            | 类型                                                                | 默认值 | 是否必填 |
| --------------- | --------------------------------------------------------------- | ------------------------------------------------------------------- | ------ | -------- |
| animation       | 动画 className                                                  | string \| Partial\<Record\<'appear' \| 'enter' \| 'leave', string>> | -      |          |
| animationAppear | 子元素第一次挂载时是否执行动画                                  | boolean                                                             | true   |          |
| component       | 包裹子元素的标签                                                | React.ElementType                                                   | 'div'  |          |
| singleMode      | 是否只有单个子元素，如果有多个子元素，请设置为 false            | boolean                                                             | true   |          |
| beforeAppear    | 执行第一次挂载动画前触发的回调函数                              | (node: HTMLElement) => void                                         | -      |          |
| onAppear        | 执行第一次挂载动画，添加 xxx-appear-active 类名后触发的回调函数 | (node: HTMLElement) => void                                         | -      |          |
| afterAppear     | 执行完第一次挂载动画后触发的函数                                | (node: HTMLElement) => void                                         | -      |          |
| beforeEnter     | 执行进场动画前触发的回调函数                                    | (node: HTMLElement) => void                                         | -      |          |
| onEnter         | 执行进场动画，添加 xxx-enter-active 类名后触发的回调函数        | (node: HTMLElement) => void                                         | -      |          |
| afterEnter      | 执行完进场动画后触发的回调函数                                  | (node: HTMLElement) => void                                         | -      |          |
| beforeLeave     | 执行离场动画前触发的回调函数                                    | (node: HTMLElement) => void                                         | -      |          |
| onLeave         | 执行离场动画，添加 xxx-leave-active 类名后触发的回调函数        | (node: HTMLElement) => void                                         | -      |          |
| afterLeave      | 执行完离场动画后触发的回调函数                                  | (node: HTMLElement) => void                                         | -      |          |

### Animate.Expand

| 参数        | 说明                                                     | 类型                                                                | 默认值 | 是否必填 |
| ----------- | -------------------------------------------------------- | ------------------------------------------------------------------- | ------ | -------- |
| animation   | 动画 className                                           | string \| Partial\<Record\<'appear' \| 'enter' \| 'leave', string>> | -      |          |
| beforeEnter | 执行进场动画前触发的回调函数                             | (node: HTMLElement) => void                                         | -      |          |
| onEnter     | 执行进场动画，添加 xxx-enter-active 类名后触发的回调函数 | (node: HTMLElement) => void                                         | -      |          |
| afterEnter  | 执行完进场动画后触发的回调函数                           | (node: HTMLElement) => void                                         | -      |          |
| beforeLeave | 执行离场动画前触发的回调函数                             | (node: HTMLElement) => void                                         | -      |          |
| onLeave     | 执行离场动画，添加 xxx-leave-active 类名后触发的回调函数 | (node: HTMLElement) => void                                         | -      |          |
| afterLeave  | 执行完离场动画后触发的回调函数                           | (node: HTMLElement) => void                                         | -      |          |

### Animate.OverlayAnimate

| 参数          | 说明                                                                                                  | 类型                                                                                                        | 默认值 | 是否必填 |
| ------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ------ | -------- |
| animation     | 动画 className                                                                                        | string \| false \| Record\<'in' \| 'out', string>                                                           | -      |          |
| visible       | 是否显示                                                                                              | boolean                                                                                                     | -      |          |
| children      | 子元素                                                                                                | ReactElement                                                                                                | -      | 是       |
| timeout       | 过渡的超时时间。                                                                                      | \| number<br/> \| { appear?: number \| undefined; enter?: number \| undefined; exit?: number \| undefined } | -      |          |
| style         | 子元素样式                                                                                            | React.CSSProperties                                                                                         | -      |          |
| mountOnEnter  | 在第一次 `in={true}` 时“惰性”挂载组件                                                                 | boolean                                                                                                     | false  |          |
| unmountOnExit | 在第一次 `in={false}` 时“惰性”卸载组件                                                                | boolean                                                                                                     | false  |          |
| onEnter       | 在“进入”状态被应用前触发的回调。<br/><br/>**签名**:<br/>**参数**:<br/>_isAppearing_: 是否在初次挂载   | (node: HTMLElement, isAppearing: boolean) => void                                                           | -      |          |
| onEntering    | 在“进入”状态被应用后触发的回调。<br/><br/>**签名**:<br/>**参数**:<br/>_isAppearing_: 是否在初次挂载   | (node: HTMLElement, isAppearing: boolean) => void                                                           | -      |          |
| onEntered     | 在“已进入”状态被应用后触发的回调。<br/><br/>**签名**:<br/>**参数**:<br/>_isAppearing_: 是否在初次挂载 | (node: HTMLElement, isAppearing: boolean) => void                                                           | -      |          |
| onExit        | 在“离开”状态被应用前触发的回调。                                                                      | (node: HTMLElement) => void                                                                                 | -      |          |
| onExiting     | 在“离开”状态被应用后触发的回调。                                                                      | (node: HTMLElement) => void                                                                                 | -      |          |
| onExited      | 在“已离开”状态被应用后触发的回调。                                                                    | (node: HTMLElement) => void                                                                                 | -      |          |
| appear        | 初次挂载时实现过渡效果                                                                                | boolean                                                                                                     | -      |          |
| enter         | 启用或禁用进场动画                                                                                    | boolean                                                                                                     | -      |          |
| exit          | 启用或禁用离场动画                                                                                    | boolean                                                                                                     | -      |          |

## Animation List

| In           | Out           |
| ------------ | ------------- |
| fadeIn       | fadeOut       |
| fadeInDown   | fadeOutDown   |
| fadeInLeft   | fadeOutLeft   |
| fadeInRight  | fadeOutRight  |
| fadeInUp     | fadeOutUp     |
| slideInDown  | slideOutUp    |
| slideInLeft  | slideOutLeft  |
| slideInRight | slideOutRight |
| slideInUp    | slideOutDown  |
| zoomIn       | zoomOut       |
| expandInDown | expandOutUp   |
| expandInUp   | expandOutDown |
| pulse        |               |


---


## avatar

# zh-CN order=0

# 基本

简单的头像展示，支持三种尺寸，两种形状。

# en-US order=0

# Basic Usage

Simple usage of Avatar component, it has 3 sizes and 2 shapes.


---


## avatar

# zh-CN order=1

# 类型

支持多种展示类型：内置图标、Icon、字符、图片，并可自定义样式

# en-US order=1

# Types

Image, Icon and letter are supported, and the latter two kinds of avatar can have custom colors and background colors.


---


## avatar

# zh-CN order=2

# 徽标

通常用于消息提示。

# en-US order=2

# With Badge

Usually used for reminders and notifications.


---


## avatar

# Avatar

-   category: Components
-   family: DataDisplay
-   chinese: 头像
-   type: 展示
-   version: 1.19

---

头像组件，1.19.0+ 版本支持。

## 何时使用

用来代表用户或事物，支持图片、图标或字符展示。

## API

### Avatar

| 参数     | 说明                                                           | 类型                                                                                                        | 默认值   | 是否必填 |
| -------- | -------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | -------- | -------- |
| children | 孩子节点列表                                                   | React.ReactNode                                                                                             | -        |          |
| size     | 头像的大小                                                     | 'small' \| 'medium' \| 'large' \| number                                                                    | 'medium' |          |
| shape    | 头像的形状                                                     | 'circle' \| 'square'                                                                                        | 'circle' |          |
| icon     | icon 类头像的图标类型，可设为 Icon 的 `type` 或 `ReactElement` | React.ReactElement \| string                                                                                | -        |          |
| src      | 图片类头像的资源地址                                           | string                                                                                                      | -        |          |
| onError  | 图片加载失败的事件，返回 false 会关闭组件默认的 fallback 行为  | () => boolean                                                                                               | -        |          |
| imgProps | 图片的其他属性                                                 | Omit\<<br/> React.ImgHTMLAttributes\<HTMLImageElement>,<br/> 'src' \| 'srcSet' \| 'onError' \| 'alt'<br/> > | -        |          |
| alt      | 图像无法显示时的 alt 替代文本                                  | string                                                                                                      | -        |          |
| srcSet   | 图片类头像响应式资源地址                                       | string                                                                                                      | -        |          |


---


## badge

# zh-CN order=7

# 无障碍支持

可通过给内容添加`className="next-sr-only"`，使内容仅能被读屏软件读取，但不会展示到页面上。

# en-US order=0

# Accessibility

Accessibility of Badge.


---


## badge

# zh-CN order=0

# 基本

简单的徽章展示，当 `count` 为 `0` 时，默认不显示，但是可以使用 `showZero` 修改为显示。

# en-US order=0

# Basic Usage

Simple usage of badge component.


---


## badge

# zh-CN order=5

# 徽标可点击

用`<a>`标签包裹组件，实现徽标本身可点击。

# en-US order=5

# Clickable Badge

Wrap Badge with `<a>` to make it clickable.


---


## badge

# zh-CN order=3

# 自定义图标、颜色等

通过 `content` 属性可以自定义徽标的内容，自定义内容不包含任何色彩样式，完全由使用者自己定义。

# en-US order=3

# Customized Content of Badge

You can set value of atrribute `content` to customize content of badge, customize content depend on what you code, and exclude any style.


---


## badge

# zh-CN order=2

# 讨嫌的小红点

没有具体的数字，仅展示小红点。

# en-US order=2

# Red Dot

Just a red dot, not a number.


---


## badge

# zh-CN order=6

# 内容动态变化

展示徽标内容动态变化的效果。

# en-US order=6

# Dynamic

Display the effect of dynamic changes.


---


## badge

# zh-CN order=4

# 独立使用

不包裹任何元素即独立使用，可自定样式展示。

# en-US order=4

# Alone Usage

Alone usage mean that badge component wrap nothing, and you can custom style of badge component.


---


## badge

# zh-CN order=1

# 封顶数字

超过`overflowCount`的数值，会显示`${overflowCount}+`，`overflowCount`默认值为`99`。

# en-US order=1

# Overflow Count

Display `\${overflowCount}+` when count is greater than `overflowCount`, default value of `overflowCount` is `99`.


---


## badge

# Badge

-   category: Components
-   family: DataDisplay
-   chinese: 徽标数
-   type: 展示

---

图标右上角的圆形徽标数字。

## 何时使用

-   一般出现在通知图标或头像的右上角，用于显示需要处理的消息条数，通过醒目视觉形式吸引用户处理。
-   在有新消息、讯息时，或者是 app/插件/功能模块可以更新、升级时使用这个组件。

## 无障碍键盘操作指南

-   `Badge`组件本身不涉及键盘操作，若可点击也应当是`Badge`与其`children`整体可聚焦点击；
-   无障碍配置方式参见[#无障碍支持](#accessibility-container)。

## API

### Badge

| 参数          | 说明                                                                | 类型             | 默认值 | 是否必填 |
| ------------- | ------------------------------------------------------------------- | ---------------- | ------ | -------- |
| children      | 徽章依托的内容                                                      | React.ReactNode  | -      |          |
| count         | 展示的数字，大于 overflowCount 时显示为 overflowCount+，为 0 时隐藏 | number \| string | 0      |          |
| content       | 自定义节点内容                                                      | React.ReactNode  | -      |          |
| overflowCount | 展示的封顶的数字                                                    | number \| string | 99     |          |
| dot           | 不展示数字，只展示一个小红点                                        | boolean          | false  |          |
| showZero      | 当 count 为 0 时，默认不显示，但是可以使用 showZero 修改为显示      | boolean          | false  |          |


---


## balloon

# zh-CN order=8&debug=true

# 无障碍支持

弹层id, 传入值才会支持无障碍。

# en-US order=8

# Accessibility

id of popup. only when you set value, balloon will support accessibility.


---


## balloon

# zh-CN order=3

# 位置

位置有十二个方向。

# en-US order=3

# Alignment

There are 12 options for align


---


## balloon

# zh-CN order=4

# 箭头指向中间

常见气泡使用类型

# en-US order=0

# Style Type

Common types of Balloon


---


## balloon

# zh-CN order=0

# 类型

常见气泡使用类型

# en-US order=0

# Style Type

Common types of Balloon


---


## balloon

# zh-CN order=4&debug=true

# 从浮层内关闭, 事件回调

使用 `visible` ,属性控制浮层显示, 使 balloon 变为受限组件。

# en-US order=4

# Control

Use 'visible' to control whether the popup should be displayed.


---


## balloon

# zh-CN order=6

# 嵌套浮层问题

浮层中如果又有浮层，比如在`Balloon`中有`DatePicker/Select`的浮层, `DatePicker`选择时，`Balloon`浮层也会关闭。可以用 `followTrigger`解决。

# en-US order=6

# Nested

When popup is nested in another popup, say DatePicker is nested in Balloon, use `followTrigger` to avoid the unexpected Balloon's closing.


---


## balloon

# zh-CN order=5&debug=true

# close按钮事件，手动控制visible

使用 `visible`,属性控制浮层显示, 使balloon变为受限组件。

# en-US order=5

# onCloseClick

When popup is nested in another popup, say DatePicker is nested in Balloon, use safeNode to avoid the unexpected Balloon's closing.


---


## balloon

# zh-CN order=7

# Tooltip使用场景

一般用于文字超长溢出等场景

# en-US order=7

# tooltip

It is generally used in the scene of text overflow.


---


## balloon

# zh-CN order=7

# Tooltip的方位

简化的Balloon, 只能设置align, trigger和children, 触发条件是hover.

# en-US order=7

# Tooltip position

Simplified Balloon, which can only set align, trigger and children, and triggered by hovering.


---


## balloon

# zh-CN order=1

# 三种触发方式

鼠标移入、聚集、点击。

# en-US order=1

# triggerType

Hover, focus and click.


---


## balloon

# Balloon

-   category: Components
-   family: Feedback
-   chinese: 气泡提示
-   type: 弹层

---

气泡组件。

## 何时使用

-   当用户与被说明对象（文字，图片，输入框等）发生交互行为的 action 开始时，即刻跟随动作出现一种辅助或帮助的提示信息。
-   其中 Balloon.Tooltip 是简化版本，主要用于 hover 时显示简单文案

### `v2` 版本更新指示

1.25 版本增加 v2 支持开启新版本弹，功能如下

-   底层更换 v2 版本弹窗组件，可根据空间动态调整位置，解决页面滚动造成弹窗脱离的问题
-   默认边缘对齐，增加 `arrowPointToCenter` 开启后箭头指向中间

## 如何使用

-   对于 trigger 是自定义的 React Component 的情况，自定义的 React Component 需要透传 onMouseEnter/onMouseLeave/onClick 事件。
-   若要使用无障碍的气泡提示，请传入 id。推荐简单提示使用`<Tooltip>`、复杂交互使用`<Balloon triggerType="click">` 。 triggerType="focus"作为辅助状态用于组件内部，请用户不要直接使用此值。

## API

### Balloon V2

| 参数               | 说明                                                                                                                                                                                                                                                | 类型                                                               | 默认值                                                   | 是否必填 | 支持版本 |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | -------------------------------------------------------- | -------- | -------- |
| v2                 | 开启 v2 版本                                                                                                                                                                                                                                        | true                                                               | -                                                        |          | 1.25     |
| children           | 浮层的内容                                                                                                                                                                                                                                          | ReactNode                                                          | -                                                        |          | -        |
| type               | 样式类型                                                                                                                                                                                                                                            | 'normal' \| 'primary'                                              | 'normal'                                                 |          | 1.23     |
| title              | 标题                                                                                                                                                                                                                                                | ReactNode                                                          | -                                                        |          | 1.23     |
| visible            | 弹层当前显示的状态                                                                                                                                                                                                                                  | boolean                                                            | -                                                        |          | -        |
| defaultVisible     | 弹层默认显示的状态                                                                                                                                                                                                                                  | boolean                                                            | false                                                    |          | -        |
| onVisibleChange    | 弹层在显示和隐藏触发的事件<br/><br/>**签名**:<br/>**参数**:<br/>_visible_: 弹层是否隐藏和显示<br/>_type_: 触发弹层显示或隐藏的来源，closeClick 表示由自带的关闭按钮触发；fromTrigger 表示由 trigger 的点击触发；docClick 表示由 document 的点击触发 | (visible: boolean, type: string) => void                           | -                                                        |          | -        |
| arrowPointToCenter | [v2] 箭头是否指向目标元素的中心                                                                                                                                                                                                                     | boolean                                                            | false                                                    |          | 1.25     |
| placementOffset    | [v2] 弹层偏离触发元素的像素值                                                                                                                                                                                                                       | number                                                             | -                                                        |          | -        |
| closable           | 是否显示关闭按钮                                                                                                                                                                                                                                    | boolean                                                            | true                                                     |          | -        |
| align              | 弹出层位置                                                                                                                                                                                                                                          | AlignType                                                          | 'b'                                                      |          | -        |
| offset             | 弹层相对于 trigger 的定位的微调，接收数组 [hoz, ver], 表示弹层在 left / top 上的增量，e.g. [100, 100] 表示往右 (RTL 模式下是往左) 、下分布偏移 100px                                                                                                | Array\<number>                                                     | [0, 0]                                                   |          | -        |
| trigger            | 触发元素                                                                                                                                                                                                                                            | ReactElement \| string                                             | <span/>                                                  |          | -        |
| triggerType        | 触发行为，鼠标悬浮，鼠标点击 ('hover','click') 或者它们组成的数组，如 ['hover', 'click'], 强烈不建议使用'focus'，若弹窗内容有复杂交互请使用 click                                                                                                   | 'hover' \| 'click' \| 'focus' \| ('hover' \| 'click' \| 'focus')[] | 'hover'                                                  |          | -        |
| onClose            | 任何 visible 为 false 时会触发的事件                                                                                                                                                                                                                | () => void                                                         | -                                                        |          | -        |
| autoAdjust         | [v2] 是否进行自动位置调整，默认自动开启                                                                                                                                                                                                             | boolean                                                            | -                                                        |          | 1.25     |
| delay              | 弹层在触发以后的延时显示，单位毫秒 ms                                                                                                                                                                                                               | number                                                             | -                                                        |          | -        |
| afterClose         | 浮层关闭后触发的事件，如果有动画，则在动画结束后触发                                                                                                                                                                                                | () => void                                                         | -                                                        |          | -        |
| autoFocus          | 弹层出现后是否自动 focus 到内部第一个元素                                                                                                                                                                                                           | boolean                                                            | true                                                     |          | -        |
| safeNode           | 安全节点：对于 triggetType 为 click 的浮层，会在点击除了浮层外的其它区域时关闭浮层.safeNode 用于添加不触发关闭的节点，值可以是 dom 节点的 id 或者是节点的 dom 对象                                                                                  | string \| ReactNode                                                | -                                                        |          | -        |
| safeId             | 用来指定 safeNode 节点的 id，和 safeNode 配合使用                                                                                                                                                                                                   | string                                                             | null                                                     |          | -        |
| animation          | 配置动画的播放方式，格式是 \{ in: '', out: '' \}，常用的动画 class 请查看 Animate 组件文档<br/><br/>**签名**:<br/>**参数**:<br/>_in_: 进场动画<br/>_out_: 出场动画                                                                                  | string \| false \| Record\<'in' \| 'out', string>                  | \{ in: 'zoomIn zoomInBig', out: 'zoomOut zoomOutBig', \} |          | -        |
| cache              | 弹层的 dom 节点关闭时是否删除                                                                                                                                                                                                                       | boolean                                                            | false                                                    |          | -        |
| popupContainer     | 指定浮层渲染的父节点，可以为节点 id 的字符串，也可以返回节点的函数。                                                                                                                                                                                | PopupProps['container']                                            | -                                                        |          | -        |
| popupStyle         | 弹层组件 style，透传给 Popup                                                                                                                                                                                                                        | CSSProperties                                                      | -                                                        |          | -        |
| popupClassName     | 弹层组件 className，透传给 Popup                                                                                                                                                                                                                    | string                                                             | -                                                        |          | -        |
| popupProps         | 弹层组件属性，透传给 Popup                                                                                                                                                                                                                          | ComponentPropsWithRef\<typeof Popup>                               | -                                                        |          | -        |
| followTrigger      | 跟随滚动                                                                                                                                                                                                                                            | boolean                                                            | -                                                        |          | -        |
| id                 | 弹层 id, 传入值才会支持无障碍                                                                                                                                                                                                                       | string                                                             | -                                                        |          | -        |

### Balloon V1

| 参数            | 说明                                                                                                                                                                                                                                                | 类型                                                               | 默认值                                                   | 是否必填 | 支持版本 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | -------------------------------------------------------- | -------- | -------- |
| v2              | 开启 v2 版本                                                                                                                                                                                                                                        | false \| undefined                                                 | -                                                        |          | 1.25     |
| children        | 浮层的内容                                                                                                                                                                                                                                          | ReactNode                                                          | -                                                        |          | -        |
| title           | 标题                                                                                                                                                                                                                                                | ReactNode                                                          | -                                                        |          | 1.23     |
| type            | 样式类型                                                                                                                                                                                                                                            | 'normal' \| 'primary'                                              | 'normal'                                                 |          | 1.23     |
| visible         | 弹层当前显示的状态                                                                                                                                                                                                                                  | boolean                                                            | -                                                        |          | -        |
| defaultVisible  | 弹层默认显示的状态                                                                                                                                                                                                                                  | boolean                                                            | false                                                    |          | -        |
| onVisibleChange | 弹层在显示和隐藏触发的事件<br/><br/>**签名**:<br/>**参数**:<br/>_visible_: 弹层是否隐藏和显示<br/>_type_: 触发弹层显示或隐藏的来源，closeClick 表示由自带的关闭按钮触发；fromTrigger 表示由 trigger 的点击触发；docClick 表示由 document 的点击触发 | (visible: boolean, type: string) => void                           | -                                                        |          | -        |
| closable        | 是否显示关闭按钮                                                                                                                                                                                                                                    | boolean                                                            | true                                                     |          | -        |
| align           | 弹出层位置                                                                                                                                                                                                                                          | AlignType                                                          | 'b'                                                      |          | -        |
| offset          | 弹层相对于 trigger 的定位的微调，接收数组 [hoz, ver], 表示弹层在 left / top 上的增量，e.g. [100, 100] 表示往右 (RTL 模式下是往左) 、下分布偏移 100px                                                                                                | Array\<number>                                                     | [0, 0]                                                   |          | -        |
| trigger         | 触发元素                                                                                                                                                                                                                                            | ReactElement \| string                                             | <span/>                                                  |          | -        |
| triggerType     | 触发行为，鼠标悬浮，鼠标点击 ('hover','click') 或者它们组成的数组，如 ['hover', 'click'], 强烈不建议使用'focus'，若弹窗内容有复杂交互请使用 click                                                                                                   | 'hover' \| 'click' \| 'focus' \| ('hover' \| 'click' \| 'focus')[] | 'hover'                                                  |          | -        |
| onClose         | 任何 visible 为 false 时会触发的事件                                                                                                                                                                                                                | () => void                                                         | -                                                        |          | -        |
| delay           | 弹层在触发以后的延时显示，单位毫秒 ms                                                                                                                                                                                                               | number                                                             | -                                                        |          | -        |
| afterClose      | 浮层关闭后触发的事件，如果有动画，则在动画结束后触发                                                                                                                                                                                                | () => void                                                         | -                                                        |          | -        |
| autoFocus       | 弹层出现后是否自动 focus 到内部第一个元素                                                                                                                                                                                                           | boolean                                                            | true                                                     |          | -        |
| safeNode        | 安全节点：对于 triggetType 为 click 的浮层，会在点击除了浮层外的其它区域时关闭浮层.safeNode 用于添加不触发关闭的节点，值可以是 dom 节点的 id 或者是节点的 dom 对象                                                                                  | string \| ReactNode                                                | -                                                        |          | -        |
| safeId          | 用来指定 safeNode 节点的 id，和 safeNode 配合使用                                                                                                                                                                                                   | string                                                             | null                                                     |          | -        |
| animation       | 配置动画的播放方式，格式是 \{ in: '', out: '' \}，常用的动画 class 请查看 Animate 组件文档<br/><br/>**签名**:<br/>**参数**:<br/>_in_: 进场动画<br/>_out_: 出场动画                                                                                  | string \| false \| Record\<'in' \| 'out', string>                  | \{ in: 'zoomIn zoomInBig', out: 'zoomOut zoomOutBig', \} |          | -        |
| cache           | 弹层的 dom 节点关闭时是否删除                                                                                                                                                                                                                       | boolean                                                            | false                                                    |          | -        |
| popupContainer  | 指定浮层渲染的父节点，可以为节点 id 的字符串，也可以返回节点的函数。                                                                                                                                                                                | PopupProps['container']                                            | -                                                        |          | -        |
| popupStyle      | 弹层组件 style，透传给 Popup                                                                                                                                                                                                                        | CSSProperties                                                      | -                                                        |          | -        |
| popupClassName  | 弹层组件 className，透传给 Popup                                                                                                                                                                                                                    | string                                                             | -                                                        |          | -        |
| popupProps      | 弹层组件属性，透传给 Popup                                                                                                                                                                                                                          | ComponentPropsWithRef\<typeof Popup>                               | -                                                        |          | -        |
| followTrigger   | 跟随滚动                                                                                                                                                                                                                                            | boolean                                                            | -                                                        |          | -        |
| id              | 弹层 id, 传入值才会支持无障碍                                                                                                                                                                                                                       | string                                                             | -                                                        |          | -        |

### Balloon.Tooltip V2

| 参数               | 说明                                                                                                                                                                          | 类型                                                               | 默认值  | 是否必填 |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ------- | -------- |
| v2                 | 开启 v2                                                                                                                                                                       | true                                                               | -       |          |
| children           | tooltip 的内容                                                                                                                                                                | ReactNode                                                          | -       |          |
| align              | 弹出层位置                                                                                                                                                                    | AlignType                                                          | 'b'     |          |
| trigger            | 触发元素                                                                                                                                                                      | ReactElement \| string                                             | <span/> |          |
| triggerType        | 触发行为，鼠标悬浮，鼠标点击 ('hover', 'click') 或者它们组成的数组，如 ['hover', 'click'], 强烈不建议使用'focus'，若有复杂交互，推荐使用 triggerType 为 click 的 Balloon 组件 | 'hover' \| 'click' \| 'focus' \| ('hover' \| 'click' \| 'focus')[] | 'hover' |          |
| popupStyle         | 弹层组件 style，透传给 Popup                                                                                                                                                  | CSSProperties                                                      | -       |          |
| popupClassName     | 弹层组件 className，透传给 Popup                                                                                                                                              | string                                                             | -       |          |
| popupProps         | 弹层组件属性，透传给 Popup                                                                                                                                                    | ComponentPropsWithRef\<typeof Popup>                               | -       |          |
| pure               | 是否 pure render                                                                                                                                                              | boolean                                                            | -       |          |
| popupContainer     | 指定浮层渲染的父节点，可以为节点 id 的字符串，也可以返回节点的函数。                                                                                                          | PopupProps['container']                                            | -       |          |
| followTrigger      | 是否跟随滚动                                                                                                                                                                  | boolean                                                            | -       |          |
| id                 | 弹层 id, 传入值才会支持无障碍                                                                                                                                                 | string                                                             | -       |          |
| delay              | 如果需要让 Tooltip 内容可被点击，可以设置这个参数，例如 100px                                                                                                                 | number                                                             | 50      |          |
| arrowPointToCenter | [v2] 箭头是否指向目标元素的中心                                                                                                                                               | boolean                                                            | false   |          |

### Balloon.Tooltip V1

| 参数           | 说明                                                                                                                                                                          | 类型                                                               | 默认值  | 是否必填 |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ------- | -------- |
| v2             | 开启 v2                                                                                                                                                                       | false \| undefined                                                 | -       |          |
| children       | tooltip 的内容                                                                                                                                                                | ReactNode                                                          | -       |          |
| align          | 弹出层位置                                                                                                                                                                    | AlignType                                                          | 'b'     |          |
| trigger        | 触发元素                                                                                                                                                                      | ReactElement \| string                                             | <span/> |          |
| triggerType    | 触发行为，鼠标悬浮，鼠标点击 ('hover', 'click') 或者它们组成的数组，如 ['hover', 'click'], 强烈不建议使用'focus'，若有复杂交互，推荐使用 triggerType 为 click 的 Balloon 组件 | 'hover' \| 'click' \| 'focus' \| ('hover' \| 'click' \| 'focus')[] | 'hover' |          |
| popupStyle     | 弹层组件 style，透传给 Popup                                                                                                                                                  | CSSProperties                                                      | -       |          |
| popupClassName | 弹层组件 className，透传给 Popup                                                                                                                                              | string                                                             | -       |          |
| popupProps     | 弹层组件属性，透传给 Popup                                                                                                                                                    | ComponentPropsWithRef\<typeof Popup>                               | -       |          |
| pure           | 是否 pure render                                                                                                                                                              | boolean                                                            | -       |          |
| popupContainer | 指定浮层渲染的父节点，可以为节点 id 的字符串，也可以返回节点的函数。                                                                                                          | PopupProps['container']                                            | -       |          |
| followTrigger  | 是否跟随滚动                                                                                                                                                                  | boolean                                                            | -       |          |
| id             | 弹层 id, 传入值才会支持无障碍                                                                                                                                                 | string                                                             | -       |          |
| delay          | 如果需要让 Tooltip 内容可被点击，可以设置这个参数，例如 100px                                                                                                                 | number                                                             | 50      |          |

## 无障碍键盘操作指南

| 按键  | 说明                                      |
| :---- | :---------------------------------------- |
| SPACE | 当`triggerType=‘click’`时，点击会弹出提示 |
| Enter | 当`triggerType=‘click’`时，点击会弹出提示 |


---


## box

# zh-CN order=3

# 垂直水平对齐

`justify` `align` 等价于`justify-contents` `align-items`，用来设置 `Box` 的主轴方向、垂直主轴方向的对齐方式，即：

-   `direction` 为 `row` 时， `align` 控制垂直方向, `justify` 控制水平方向；
-   `direction` 为 `column` 时(默认值)， `justify` 控制垂直方向, `align` 控制水平方向。

# en-US order=3

# align and justify

`justify` `align` same as `justify-contents` `align-items`


---


## box

# zh-CN order=0

# 基本

简单的弹性布局展示，可以通过 `spacing` 控制子元素的间距。

# en-US order=0

# Basic Usage

Simple usage of Box component.


---


## box

# zh-CN order=1

# 排布方向

默认子元素的排布方向为 `column` ， 可以通过 `direction` 参数修改为 `row`。

# en-US order=1

# Direction

Direction is `column` by default, you can set it to `row`.


---


## box

# zh-CN order=2

# 内外边距

可以通过 `padding` `margin` 设置 `Box` 的内、外边距， `[10, 5]` 表示上下方向为10，左右方向为5。

# en-US order=2

# Padding and Margin

Use `padding` `margin` directly, same as `<Box style={{padding, margin}}>`, [10, 5] stands for 10 of top & bottom, 5 of left & right.


---


## box

# zh-CN order=4

# 折行

默认不折行，可以通过设置 `wrap` 控制折行。 受浏览器限制，本功能支持到IE11+。

# en-US order=4

# wrap

`wrap` is false by default. Support IE11+.


---


## box

# Box

-   category: Components
-   family: General
-   chinese: 弹性布局
-   type: 展示
-   version: 1.19

---

弹性布局组件，支持版本1.19.0+。

## 何时使用

-   用于弹性布局, 通过`display: flex`实现。
-   受浏览器限制，本功能支持到IE10+，IE下[#参考文档](<https://docs.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/dev-guides/hh673531(v=vs.85%3E)>)。

## FAQ

### 为何嵌套自定义组件，间距没有生效？

自定义组件的间距是 `Box` 算出来，同style透传给子组件的，因此子组件需要至少透传style属性；

```jsx
// wrong
function Foo() {
    return <div />;
}

// correct
function Foo({ style }) {
    return <div style={style} />;
}
```

## API

### Box

| 参数      | 说明                                                            | 类型                                                                                                  | 默认值   | 是否必填 |
| --------- | --------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | -------- | -------- |
| flex      | 同 CSS 属性 `flex`，支持数组方式设置                            | \| CSS.Property.Flex<br/> \| [CSS.Property.FlexGrow, CSS.Property.FlexShrink, CSS.Property.FlexBasis] | -        |          |
| direction | 布局方向，同 CSS 属性 `flex-direction`                          | CSS.Property.FlexDirection                                                                            | 'column' |          |
| wrap      | 是否折行                                                        | boolean                                                                                               | false    |          |
| spacing   | 元素之间的间距                                                  | Spacing                                                                                               | -        |          |
| margin    | 容器外间距                                                      | Spacing                                                                                               | -        |          |
| padding   | 容器内间距                                                      | Spacing                                                                                               | -        |          |
| justify   | 沿着主轴方向，子元素们的排布关系，同 CSS 属性 `justify-content` | CSS.Property.JustifyContent                                                                           | -        |          |
| align     | 沿交叉轴方向，子元素们的排布关系，同 CSS 属性 `align-items`     | CSS.Property.AlignItems                                                                               | -        |          |
| component | 定制 JSX 标签名                                                 | keyof React.JSX.IntrinsicElements                                                                     | 'div'    |          |

### Spacing

```typescript
export type Spacing =
    | number
    | [topAndBottom: number, rightAndLeft: number]
    | [top: number, rightAndLeft: number, bottom: number]
    | [top: number, right: number, bottom: number, left: number];
```


---


## breadcrumb

# zh-CN order=2

# 自动省略

自动显示省略号。

# en-US order=2

# Show Omission

The ellipses are displayed automatically when Breadcrumb overflow.


---


## breadcrumb

# zh-CN order=0

# 基本用法

使用 `Breadcrumb.Item` 来设置面包屑子节点，如果设置其 `link` 属性就是 `<a />` 节点，否则为 `<span />` 节点。

# en-US order=0

# Basic Usage

Use `Breadcrumb.Item` to set the breadcrumb subnode, if its `link` properity is set to be a `<a />` node, otherwise it is a `<span />`.


---


## breadcrumb

# zh-CN order=5

# 自定义节点

可以自定义面包屑的节点，比如 react 路由。

# en-US order=5

# Set Separator

You can put your content in BreadCrumb.Item, like ReactRouter.


---


## breadcrumb

# zh-CN order=1

# 显示省略

当超过设置的最大个数的时候，显示省略号。

# en-US order=1

# Show Omission

When the maximum number of settings is exceeded, the ellipses are displayed.


---


## breadcrumb

# zh-CN order=4

# 设置分隔符

也可以设置不同的分隔符。

# en-US order=4

# Set Separator

You can also set specific separators.


---


## breadcrumb

# zh-CN order=3

# 省略号可点击展开

点击省略号展示被隐藏的项。

# en-US order=3

# Show Omission

Hidden items will be displayed when ellipses clicked.


---


## breadcrumb

# Breadcrumb

-   category: Components
-   family: Navigation
-   chinese: 面包屑
-   type: 导航
-   cols: 1

---

面包屑组件。

## 何时使用

用来告知用户当前的位置，以及当前页面在整个网站中的位置，属于一种辅助的导航方式，适用于清晰且具多层次结构的网站，每一层内容为层级归属关系，方便用户返回上一级或各个层级的页面。

## API

### Breadcrumb

| 参数            | 说明                                                               | 类型                                                                                                | 默认值 | 是否必填 | 支持版本 |
| --------------- | ------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- | ------ | -------- | -------- |
| children        | 面包屑子节点，需传入 Breadcrumb.Item                               | \| Array\<React.ReactElement\<ItemProps> \| boolean \| null><br/> \| React.ReactElement\<ItemProps> | -      |          | -        |
| maxNode         | 面包屑最多显示个数，超出部分会被隐藏                               | number \| 'auto'                                                                                    | 100    |          | -        |
| showHiddenItems | 当超过的项被隐藏时，是否可通过点击省略号展示菜单（包含被隐藏的项） | boolean                                                                                             | false  |          | 1.23     |
| popupContainer  | 弹层挂载的容器节点（在showHiddenItems为true时才有意义）            | DropdownProps['container']                                                                          | -      |          | 1.23     |
| followTrigger   | 是否跟随trigger滚动（在showHiddenItems为true时才有意义）           | boolean                                                                                             | -      |          | 1.23     |
| popupProps      | 添加到弹层上的属性（在showHiddenItems为true时才有意义）            | DropdownProps                                                                                       | -      |          | 1.23     |
| separator       | 分隔符，可以是文本或 Icon                                          | string \| React.ReactNode                                                                           | -      |          | -        |
| component       | 设置标签类型                                                       | React.ComponentType\<BreadcrumbProps> \| string                                                     | 'nav'  |          | -        |

### Breadcrumb.Item

| 参数    | 说明                                                                     | 类型                                  | 默认值 | 是否必填 |
| ------- | ------------------------------------------------------------------------ | ------------------------------------- | ------ | -------- |
| link    | 面包屑节点链接，如果设置这个属性，则该节点为`<a />` ，否则是`<span />`   | string                                | -      |          |
| onClick | 元素点击事件<br/><br/>**签名**:<br/>**参数**:<br/>_e_: Click Mouse Event | React.MouseEventHandler\<HTMLElement> | -      |          |

## 无障碍键盘操作指南

| 按键 | 说明         |
| :--- | :----------- |
| Tab  | 切换到下一项 |


---


## button

# zh-CN order=8

# 无障碍支持

在使用不包含文本的icon Button组件时，我们需要添加`aria-label`对其进行描述，键盘操作请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=8

# Accessibility

When using icon Button component , we should add `aria-label` to describe it. Please refer to `ARIA and KeyBoard` for keyboard operation information.


---


## button

# zh-CN order=1

# 按钮标签

默认情况下 Button 组件使用 `<button>` 标签来渲染按钮，通过 `component` 属性可以自定义 Button 的标签类型。可选值为 `button` 和 `a`。

# en-US order=1

# Custom component

By default, a Button component is rendered by a html `<button>` tag, its render behavior could be modified by a props named `component`, which should be set to `button` or `a`.


---


## button

# zh-CN order=2

# 禁用状态

添加 `disabled` 属性即可让按钮处于不可用状态，同时按钮样式也会改变。

# en-US order=2

# Disabled

Disable a Button by adding `disabled` attribute.


---


## button

# zh-CN order=4

# 幽灵按钮

幽灵按钮通常用在有色背景下，可以使用 `ghost` 属性开启，此时 Button 为透明背景。对于浅色背景和深色背景，通过取值 `light`, `dark` 可以配置使用幽灵按钮的场景。

# en-US order=4

# Ghost

Ghost button is usually used for colored backgrounds. Change a Button to ghost by adding `ghost` attribute,
and set the attribute's value to `light` or `darked` based on the color depth.


---


## button

# zh-CN order=7

# 按钮组

`Button.Group` 子组件用于将多个按钮组合在一个容器中。

# en-US order=7

# Button group

`Button.Group` could be used to combine multiple Buttons.


---


## button

# zh-CN order=5

# 图标按钮

`Button` 可以嵌入 `Icon`，默认情况下 `Icon` 尺寸自动跟随 `Button` 的尺寸，可以通过 `iconSize` 属性进行设置。

通过设置 `icons` 属性中的 `loading` 即可自定义加载的 `icon`。

# en-US order=5

# Icon

Button could contain Icon as its children, the default size of Icon is controlled by the Button size. And it can be manually controlled by using `iconSize` prop.


---


## button

# zh-CN order=3

# 加载状态

通过设置 `loading` 属性即可以让按钮处于加载状态。

# en-US order=3

# Loading

Button has a inner state `loading` to control if a Button is in loading. It could be changed by setting `loading` attribute.


---


## button

# zh-CN order=6

# 按钮尺寸

可以通过设置 `size` 属性控制按钮的尺寸，可选值为 `large` `medium` `small`，其中默认值为 `medium`。

# en-US order=6

# Size

The size of a Button is controlled by a `size` attribute, supporting `large`, `medium`, `small`, the default value is `medium`.


---


## button

# zh-CN order=0

# 按钮类型

按钮有三种视觉层次：主按钮、次按钮、普通按钮。不同的类型可以用来区别按钮的重要程度。

默认情况下 Button 组件使用 `<button>` 标签来渲染按钮，通过 `component` 属性可以自定义 Button 的标签类型。
可选值为 `button` 和 `a`。

# en-US order=0

# Type

The types of button includes: primary, secondary, normal. Each one used to describe the importance level of a button.


---


## button

# Button

-   category: Components
-   family: General
-   chinese: 按钮
-   type: 表单

---

按钮用于开始一个即时操作。

## 何时使用

-   标记一个（或封装一组）操作命令，响应用户点击行为，触发相应的业务逻辑。

## API

### Button

| 参数      | 说明                        | 类型                                                                                                                                              | 默认值                                                                                                         | 是否必填 |
| --------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------- |
| type      | 按钮的类型                  | 'primary' \| 'secondary' \| 'normal'                                                                                                              | 'normal'                                                                                                       |          |
| size      | 按钮的尺寸                  | ButtonSize                                                                                                                                        | 'medium'                                                                                                       |          |
| icons     | 按钮中可配置的 Icon         | { loading?: React.ReactNode }                                                                                                                     | -                                                                                                              |          |
| iconSize  | 按钮中 Icon 的尺寸          | \| number<br/> \| 'xxs'<br/> \| 'xs'<br/> \| 'small'<br/> \| 'medium'<br/> \| 'large'<br/> \| 'xl'<br/> \| 'xxl'<br/> \| 'xxxl'<br/> \| 'inherit' | 默认根据 size 自动映射，映射规则：<br/>size:large -\> `small`<br/>size:medium -\> `xs`<br/>size:small -\> `xs` |          |
| htmlType  | button 标签的 type 值       | 'submit' \| 'reset' \| 'button'                                                                                                                   | 'button'                                                                                                       |          |
| component | 最终渲染的 jsx 标签标签类型 | 'button' \| 'a' \| React.ComponentType\<unknown>                                                                                                  | -                                                                                                              |          |
| loading   | 设置按钮的载入状态          | boolean                                                                                                                                           | false                                                                                                          |          |
| ghost     | 是否为幽灵按钮              | true \| false \| 'light' \| 'dark'                                                                                                                | false                                                                                                          |          |
| text      | 是否为文本按钮              | boolean                                                                                                                                           | false                                                                                                          |          |
| warning   | 是否为警告按钮              | boolean                                                                                                                                           | false                                                                                                          |          |
| disabled  | 是否禁用                    | boolean                                                                                                                                           | false                                                                                                          |          |
| onClick   | 点击按钮的回调              | React.MouseEventHandler                                                                                                                           | -                                                                                                              |          |

### Button.Group

| 参数 | 说明                           | 类型       | 默认值 | 是否必填 |
| ---- | ------------------------------ | ---------- | ------ | -------- |
| size | 统一设置 Button 组件的按钮大小 | ButtonSize | -      |          |

### ButtonSize

按钮类型

```typescript
export type ButtonSize = 'small' | 'medium' | 'large';
```

## 无障碍键盘操作指南

| 按键  | 说明            |
| :---- | :-------------- |
| Enter | 触发onClick事件 |
| SPACE | 触发onClick事件 |


---


## calendar

# zh-CN order=0

# 全屏日历

最简单的日历用法，用户可以切换年/月。

# en-US order=0

# Fullscreen

A basic fullscreen calendar.


---


## calendar

# zh-CN order=1

# 日历卡片

可以将 `card` 形态的日历组件嵌套在宽高受限的容器中。

# en-US order=1

# Card

A card calendar is usually used for embedding in a container with limiting width and height.


---


## calendar

# zh-CN order=3

# 定制日历内容

通过 `dateCellRender` 和 `monthCellRender` 用户可以在日历中添加自定义内容。

# en-US order=3

# Custom cell

Render custom contents in `dateCellRender` and `monthCellRender`.


---


## calendar

# zh-CN order=4

# 日历默认展示月份

日历组件默认使用当前月作为展示的月份，用户可以可以通过 `defaultVisibleMonth` 属性进行定制。并可以通过 `onVisibleMonthChange` 属性监听面板可视月份的变化。

# en-US order=4

# Default visible month

Change default visible month by `defaultVisibleMonth`.


---


## calendar

# zh-CN order=2

# 禁用日期

可以通过 `disabledDate` 属性禁止用户选择某些日期。

# en-US order=2

# Disable dates

Disable specific dates by `disabledDate`.


---


## calendar

# zh-CN order=6

# 多语言

日期时间的多语言来源于 moment ，可以通过 `moment.locale('zh-cn')` 来设置显示中文。

# en-US order=6

# Value Locale

Locale of date values come from `moment`, setting to dispaly Chinese with `moment.locale('zh-cn')`.


---


## calendar

# zh-CN order=0

# 农历

农历

# en-US order=0

# Lunar Calendar

A Lunar calendar.


---


## calendar

# zh-CN order=5

# 日历面板

日历面板通用用于嵌套在弹层容器中。

# en-US order=5

# Panel

A calendar panel is usually used for embedding in a popup container.


---


## calendar

# Calendar

-   category: Components
-   family: DataDisplay
-   chinese: 日历
-   type: 展示

---

按照日历形式展示数据的容器。

## 何时使用

日历组件是一个偏向于展示与受控的基础组件，可用于日程、课表、价格日历、农历展示等。

## 如何使用

日期值的多语言设置：由于 Calendar 组件内部使用 moment 对象来设置日期（请使用最新版 moment），部分 Locale 读取自 moment，因此用户需要在外部使用时[正确的设置 moment 的 locale](http://momentjs.cn/docs/#/i18n/changing-locale/) 。

```js
import moment from 'moment';

moment.locale('zh-cn');
```

## API

### Calendar

| 参数                 | 说明                                                                                             | 类型                                                    | 默认值                    | 是否必填 |
| -------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------- | ------------------------- | -------- |
| defaultValue         | 默认选中的日期（moment 对象）                                                                    | Moment \| null                                          | -                         |          |
| shape                | 展现形态                                                                                         | 'card' \| 'fullscreen' \| 'panel'                       | 'fullscreen'              |          |
| value                | 选中的日期值 (moment 对象)                                                                       | Moment \| null                                          | -                         |          |
| mode                 | 面板模式                                                                                         | CalendarMode                                            | -                         |          |
| showOtherMonth       | 是否展示非本月的日期                                                                             | boolean                                                 | true                      |          |
| defaultVisibleMonth  | 默认展示的月份                                                                                   | () => Moment \| null                                    | -                         |          |
| onModeChange         | 面板模式变化时的回调<br/><br/>**签名**:<br/>**参数**:<br/>_mode_: 对应面板模式 date, month, year | (mode: CalendarMode) => void                            | -                         |          |
| onSelect             | 选择日期单元格时的回调                                                                           | (value: Moment) => void                                 | -                         |          |
| onVisibleMonthChange | 展现的月份变化时的回调                                                                           | (value: Moment, reason: VisibleMonthChangeType) => void | -                         |          |
| dateCellRender       | 自定义日期渲染函数                                                                               | (value: Moment) => React.ReactNode                      | value =\> value.date()    |          |
| monthCellRender      | 自定义月份渲染函数                                                                               | (calendarDate: Moment) => React.ReactNode               | -                         |          |
| disabledDate         | 不可选择的日期                                                                                   | (calendarDate: Moment, view: CalendarMode) => boolean   | -                         |          |
| modes                | 面板可变化的模式列表，仅初始化时接收一次                                                         | CalendarMode[]                                          | ['date', 'month', 'year'] |          |
| format               | 日期值的格式（用于日期 title 显示的格式）                                                        | string                                                  | 'YYYY-MM                  |          |
| yearRange            | 年份范围，[START_YEAR, END_YEAR] (只在 shape 为‘card’, 'fullscreen' 下生效)                      | [start: number, end: number]                            | -                         |          |

### Calendar.RangeCalendar

| 参数                 | 说明                                                                        | 类型                                                    | 默认值                 | 是否必填 |
| -------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------- | ---------------------- | -------- |
| mode                 | 面板模式                                                                    | CalendarMode                                            | 'date'                 |          |
| format               | 日期值的格式（用于日期 title 显示的格式）                                   | string                                                  | 'YYYY-MM               |          |
| dateCellRender       | 自定义日期渲染函数                                                          | (value: Moment) => React.ReactNode                      | value =\> value.date() |          |
| onSelect             | 选择日期单元格时的回调                                                      | (value: Moment) => void                                 | -                      |          |
| onVisibleMonthChange | 展现的月份变化时的回调                                                      | (value: Moment, reason: VisibleMonthChangeType) => void | -                      |          |
| showOtherMonth       | 是否展示非本月的日期                                                        | boolean                                                 | true                   |          |
| startValue           | 开始日期（moment 对象）                                                     | Moment \| null                                          | -                      |          |
| endValue             | 结束日期（moment 对象）                                                     | Moment \| null                                          | -                      |          |
| defaultStartValue    | 默认的开始日期（moment 对象）                                               | Moment \| null                                          | -                      |          |
| defaultEndValue      | 默认的结束日期（moment 对象）                                               | Moment \| null                                          | -                      |          |
| monthCellRender      | 自定义月份渲染函数                                                          | (calendarDate: Moment) => React.ReactNode               | -                      |          |
| defaultVisibleMonth  | 默认展示的月份                                                              | () => Moment \| null                                    | -                      |          |
| disabledDate         | 不可选择的日期                                                              | (calendarDate: Moment, view: CalendarMode) => boolean   | -                      |          |
| shape                | 展现形态                                                                    | 'card' \| 'fullscreen' \| 'panel'                       | -                      |          |
| yearRange            | 年份范围，[START_YEAR, END_YEAR] (只在 shape 为‘card’, 'fullscreen' 下生效) | [number, number]                                        | -                      |          |

### CalendarMode

```typescript
export type CalendarMode = 'date' | 'month' | 'year';
```

### VisibleMonthChangeType

```typescript
export type VisibleMonthChangeType = 'cellClick' | 'buttonClick' | 'yearSelect' | 'monthSelect';
```


---


## calendar2

# zh-CN order=0

# 基础日历

最简单的日历用法，用户可以切换年/月。

# en-US order=0

# Basic

A basic calendar.


---


## calendar2

# zh-CN order=1

# 卡片日历

卡片日历通常用来被嵌套在宽高受限的容器中。

# en-US order=1

# Card

A card calendar is usually used for embedding in a container with limited width and height.


---


## calendar2

# zh-CN order=6

# 定制日历内容

通过 `dateCellRender` 和 `monthCellRender`， 可以在日历中添加自定义内容。

# en-US order=6

# Custom cell

Render custom contents by `dateCellRender` and `monthCellRender`.


---


## calendar2

# zh-CN order=5

# 日历默认展示月份

日历组件默认使用当前月作为展示的月份，用户可以可以通过 `defaultPanelValue` 属性进行定制。并可以通过 `onPanelChange` 属性监听面板可视月份的变化。

# en-US order=5

# Default visible month

Change default visible month by `defaultPanelValue`.


---


## calendar2

# zh-CN order=4

# 禁用日期

可以通过 `disabledDate` 属性禁止用户选择某些日期。

# en-US order=4

# Disable dates

Disable specific dates by `disabledDate`.


---


## calendar2

# zh-CN order=3

# 农历

农历

# en-US order=3

# Lunar Calendar

A lunar calendar.


---


## calendar2

# zh-CN order=2

# 面板日历

面板日历通常用来被嵌套在弹层容器中。

# en-US order=2

# Panel

A panel calendar is usually used for embedding in a popup container.


---


## calendar2

# Calendar2

-   category: Components
-   family: DataDisplay
-   chinese: 日历2
-   type: 展示

---

按照日历形式展示数据的容器。

### 何时使用

1.22版本增加当前组件

日历组件是一个偏向于展示与受控的基础组件，可用于日程、课表、价格日历、农历展示等。

### 国际化

由于 `Calendar` 组件内部使用 `dayjs` 对象来设置日期（请使用最新版 dayjs），部分 `Locale` 读取自 [日期库`dayjs`的国际化](https://dayjs.gitee.io/docs/zh-CN/i18n/i18n)。

```js
import { DatePicker2, ConfigProvider } from '@alifd/next';
import 'dayjs/locale/en';
import en from '@alifd/next/lib/locale/en-us';

function App() {
    return (
        <ConfigProvider locale={en}>
            <DatePicker2 />
        </ConfigProvider>
    );
}
ReactDOM.render(<App />, mountNode);
```

## API

### Calendar

| 参数              | 说明                                   | 类型                                                                                                                                                                                                                                                                                                     | 默认值       | 是否必填 |
| ----------------- | -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | -------- |
| defaultValue      | 默认选中的日期（dayjs 对象）           | ConfigType                                                                                                                                                                                                                                                                                               | -            |          |
| value             | 选中的日期值 (dayjs 对象)              | ConfigType                                                                                                                                                                                                                                                                                               | -            |          |
| defaultPanelValue | 面板默认显示的日期                     | ConfigType                                                                                                                                                                                                                                                                                               | -            |          |
| panelValue        | 面板显示的日期（受控）                 | ConfigType                                                                                                                                                                                                                                                                                               | -            |          |
| shape             | 展现形态                               | 'card' \| 'fullscreen' \| 'panel'                                                                                                                                                                                                                                                                        | 'fullscreen' |          |
| mode              | 日期模式                               | CalendarMode                                                                                                                                                                                                                                                                                             | 'month'      |          |
| panelMode         | 面板模式，未指定时会根据 mode 自动推断 | CalendarPanelMode                                                                                                                                                                                                                                                                                        | -            |          |
| onSelect          | 选择日期单元格时的回调                 | (value: Dayjs, strVal: string) => void                                                                                                                                                                                                                                                                   | -            |          |
| onChange          | 值改变时的回调                         | (value: Dayjs, strVal: string) => void                                                                                                                                                                                                                                                                   | -            |          |
| onPanelChange     | 日期面板变化回调                       | (value: Dayjs, mode: string, reason?: string) => void                                                                                                                                                                                                                                                    | -            |          |
| className         | 自定义样式类                           | string                                                                                                                                                                                                                                                                                                   | -            |          |
| dateCellRender    | 自定义日期渲染                         | CustomCellRender                                                                                                                                                                                                                                                                                         | -            |          |
| monthCellRender   | 自定义月份渲染函数                     | CustomCellRender                                                                                                                                                                                                                                                                                         | -            |          |
| yearCellRender    | 自定义年份渲染函数                     | CustomCellRender                                                                                                                                                                                                                                                                                         | -            |          |
| quarterCellRender | 自定义季度渲染函数                     | CustomCellRender                                                                                                                                                                                                                                                                                         | -            |          |
| disabledDate      | 不可选择的日期                         | (value: Dayjs, mode: CalendarPanelMode) => boolean                                                                                                                                                                                                                                                       | -            |          |
| onPrev            | 点击头部左单箭头时触发的回调           | OnPrevOrNext                                                                                                                                                                                                                                                                                             | -            |          |
| onNext            | 点击头部右单箭头时触发的回调           | OnPrevOrNext                                                                                                                                                                                                                                                                                             | -            |          |
| onSuperPrev       | 点击头部左双箭头时触发的回调           | OnPrevOrNext                                                                                                                                                                                                                                                                                             | -            |          |
| onSuperNext       | 点击头部右双箭头时触发的回调           | OnPrevOrNext                                                                                                                                                                                                                                                                                             | -            |          |
| headerRender      | 头部自定义渲染                         | (props: HeaderPanelProps) => React.ReactNode                                                                                                                                                                                                                                                             | -            |          |
| validValue        | 可选择的年份的有效区间                 | [Dayjs, Dayjs]                                                                                                                                                                                                                                                                                           | -            |          |
| renderHeaderExtra | 渲染头部额外内容                       | (props: HeaderPanelProps) => React.ReactNode                                                                                                                                                                                                                                                             | -            |          |
| cellClassName     | 单元格自定义样式                       | (value: Dayjs) => Record\<string, boolean> \| undefined \| null                                                                                                                                                                                                                                          | -            |          |
| cellProps         | 单元格自定义属性                       | {<br/> onMouseEnter?: (<br/> v: Dayjs,<br/> e: React.MouseEvent\<HTMLElement>,<br/> args: Pick\<CellData, 'isCurrent' \| 'label'><br/> ) => void;<br/> onMouseLeave?: (<br/> v: Dayjs,<br/> e: React.MouseEvent\<HTMLElement>,<br/> args: Pick\<CellData, 'isCurrent' \| 'label'><br/> ) => void;<br/> } | -            |          |

### CellData

| 参数      | 说明 | 类型             | 默认值 | 是否必填 |
| --------- | ---- | ---------------- | ------ | -------- |
| value     | -    | Dayjs            | -      | 是       |
| label     | -    | number \| string | -      | 是       |
| isCurrent | -    | boolean          | -      | 是       |
| key       | -    | string \| number | -      | 是       |

### OnPrevOrNext

```typescript
export type OnPrevOrNext = (value: Dayjs, options: { unit: ManipulateType; num: number }) => void;
```

### CalendarMode

```typescript
export type CalendarMode = 'month' | 'year';
```

### CalendarPanelMode

```typescript
export type CalendarPanelMode = 'date' | 'week' | 'month' | 'quarter' | 'year' | 'decade';
```

### CustomCellRender

```typescript
export type CustomCellRender = (value: Dayjs) => React.ReactNode;
```


---


## card

# zh-CN order=0

# 基本

最简单的用法。

# en-US order=0

# Basic

A simple card with title and sub-title.


---


## card

# zh-CN order=4

# 分割线

卡片分割线

# en-US order=4

# Divider

Card Divider


---


## card

# zh-CN order=5

# 自定义卡片

与子组件的组合来自定义卡片样式

# en-US order=5

# Free Mode

Combination with subcomponents to customize card styles


---


## card

# zh-CN order=4

# 多媒体内容

下面是一个使用图像来增强内容的卡片示例。

# en-US order=4

# Media Content

Here is an example of a card that uses images to enhance content.


---


## card

# zh-CN order=5

# 无边框模式

最简单的用法。

# en-US order=5

# Noborder

A simple card widthout border.


---


## card

# Card

-   category: Components
-   family: DataDisplay
-   chinese: 卡片
-   type: 基本

---

一个通用的卡片组件。

## 何时使用

当一个模块的同类信息不能自然形成区块感，可借助 Card 组件将信息整合，帮助界面信息模块感更强。

## API

### Card

| 参数            | 说明                                                                                             | 类型             | 默认值 | 是否必填 | 支持版本 |
| --------------- | ------------------------------------------------------------------------------------------------ | ---------------- | ------ | -------- | -------- |
| media           | 卡片的上的图片 / 视频                                                                            | ReactNode        | -      |          | -        |
| title           | 卡片的标题                                                                                       | ReactNode        | -      |          | -        |
| subTitle        | 卡片的副标题                                                                                     | ReactNode        | -      |          | -        |
| actions         | 卡片操作组，位置在卡片底部                                                                       | ReactNode        | -      |          | -        |
| showTitleBullet | 是否显示标题的项目符号                                                                           | boolean          | true   |          | -        |
| showHeadDivider | 是否展示头部的分隔线                                                                             | boolean          | true   |          | -        |
| contentHeight   | 内容区域的固定高度                                                                               | string \| number | 120    |          | -        |
| extra           | 标题区域的用户自定义内容                                                                         | ReactNode        | -      |          | -        |
| free            | 是否开启自由模式，开启后 card 将使用子组件配合使用，设置此项后 title, subtitle, 等等属性都将失效 | boolean          | false  |          | -        |
| hasBorder       | 是否带边框                                                                                       | boolean          | true   |          | 1.24     |

### Card.Media

| 参数      | 说明           | 类型        | 默认值 | 是否必填 |
| --------- | -------------- | ----------- | ------ | -------- |
| component | 设置标签类型   | ElementType | 'div'  |          |
| image     | 背景图片地址   | string      | -      |          |
| src       | 媒体源文件地址 | string      | -      |          |

### Card.Header

| 参数      | 说明                     | 类型        | 默认值 | 是否必填 |
| --------- | ------------------------ | ----------- | ------ | -------- |
| title     | 卡片的标题               | ReactNode   | -      |          |
| subTitle  | 卡片的副标题             | ReactNode   | -      |          |
| extra     | 标题区域的用户自定义内容 | ReactNode   | -      |          |
| component | 设置标签类型             | ElementType | 'div'  |          |

### Card.Content

| 参数      | 说明         | 类型        | 默认值 | 是否必填 |
| --------- | ------------ | ----------- | ------ | -------- |
| component | 设置标签类型 | ElementType | 'div'  |          |

### Card.Divider

| 参数      | 说明               | 类型        | 默认值 | 是否必填 |
| --------- | ------------------ | ----------- | ------ | -------- |
| component | 设置标签类型       | ElementType | 'hr'   |          |
| inset     | 分割线是否向内缩进 | boolean     | -      |          |

### Card.Actions

| 参数      | 说明         | 类型        | 默认值 | 是否必填 |
| --------- | ------------ | ----------- | ------ | -------- |
| component | 设置标签类型 | ElementType | 'div'  |          |


---


## cascader

# zh-CN order=0

# 基本使用

展示基本的单选用法。

# en-US order=0

# Basic Usage

Demo the basic single select usage.


---


## cascader

# zh-CN order=5

# 设置父子节点选中是否关联

通过`checkStrictly`设置父子节点是否关联选中状态，，仅在多选情况下有效。

# en-US order=5

# Set parent or child nodes to select whether to relate

Demo whether parent and child nodes checked is related.


---


## cascader

# zh-CN order=5

# 自定义样式

可以通过`listStyle`，`listClassName`来定制组件宽高，通过`itemRender`自定字节。

# en-US order=5

# Customize Style

You can customize the component width and height with `listStyle` and `listClassName`.


---


## cascader

# zh-CN order=4

# 异步加载数据

通过`loadData`动态获取数据，`isLeaf`属性用于标志是否是叶子节点。

# en-US order=4

# Loading data asynchronously

Demon loading data asynchronously.


---


## cascader

# zh-CN order=1

# 展开触发行为

展示可通过`expandTriggerType`来设置不同的展开触发行为，支持`click`和`hover`，默认值为`click`。

# en-US order=1

# Expand trigger type

You can set expand trigger type by setting `expandTriggerType`, support `click` and `hover`, the default is `click`.


---


## cascader

# zh-CN order=2

# 多选

设置`multiple`为`true`，开启多选，此时节点可勾选。

# en-US order=2

# Multiple select

Demo the basic multiple select usage.


---


## cascader

# zh-CN order=3

# 设置是否只能选择叶子项

单选的时候通过`canOnlySelectLeaf`属性设置是否仅叶子节点可选中；多选的时候通过`canOnlyCheckLeaf`属性设置是否仅叶子节点可勾选。

# en-US order=3

# Set whether to only select leaf items

Demo whether it can only select leaf items.


---


## cascader

# Cascader

-   category: Components
-   family: DataDisplay
-   chinese: 级联
-   type: 基本

---

级联组件。

## 何时使用

-   适用于从一组具有关联性的数据集合中进行选择的交互方式。
-   由于子集目录隐藏，级联是一种节约屏幕空间的有效方法。
-   级别数因业务需求而定，建议不超过5级。
-   级联多用于表单场景，可以独立在页面中使用，也可以与其他元素组合使用，如级联选择。

## API

### Cascader

Cascader 支持属性透传给 Menu，但会忽略 onSelect、value、onChange、defaultValue、focusedKey、onItemFocus、focusable、isSelectIconRight、onBlur 等和 Cascader 同名的属性

| 参数                 | 说明                                                                                                                                                                                                                                                                | 类型                                                                                                                              | 默认值                                  | 是否必填 | 支持版本 |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- | -------- | -------- |
| dataSource           | 数据源                                                                                                                                                                                                                                                              | Array\<CascaderDataItem>                                                                                                          | []                                      |          | -        |
| defaultValue         | （非受控）默认值                                                                                                                                                                                                                                                    | string \| Array\<string>                                                                                                          | -                                       |          | -        |
| value                | （受控）当前值                                                                                                                                                                                                                                                      | string \| Array\<string>                                                                                                          | -                                       |          | -        |
| onChange             | 选中值改变时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 选中的值，单选时返回单个值，多选时返回数组<br/>_data_: 选中的数据，包括 value 和 label，单选时返回单个值，多选时返回数组，父子节点选中关联时，同时选中，只返回父节点<br/>_extra_: 额外参数 | (<br/> value: string \| Array\<string>,<br/> data: CascaderDataItem \| Array\<CascaderDataItem>,<br/> extra: Extra<br/> ) => void | -                                       |          | -        |
| onSelect             | 选中时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_v_: 选中的值<br/>_data_: 选中的数据，包括 value 和 label<br/>_extra_: 额外参数                                                                                                                           | (v: string, data: CascaderDataItemWithPosInfo, extra: Extra) => void                                                              | -                                       |          | -        |
| defaultExpandedValue | （非受控）默认展开值                                                                                                                                                                                                                                                | Array\<string>                                                                                                                    | -                                       |          | -        |
| expandedValue        | （受控）当前展开值                                                                                                                                                                                                                                                  | Array\<string>                                                                                                                    | -                                       |          | -        |
| expandTriggerType    | 展开触发的方式                                                                                                                                                                                                                                                      | 'click' \| 'hover'                                                                                                                | 'click'                                 |          | -        |
| onExpand             | 展开时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_expandedValue_: 各列展开值的数组                                                                                                                                                                         | (expandedValue: Array\<string>) => void                                                                                           | -                                       |          | -        |
| useVirtual           | 是否开启虚拟滚动，开启后建议设置 listStyle 固定列宽                                                                                                                                                                                                                 | boolean                                                                                                                           | false                                   |          | -        |
| multiple             | 是否多选                                                                                                                                                                                                                                                            | boolean                                                                                                                           | false                                   |          | -        |
| canOnlySelectLeaf    | 单选时是否只能选中叶子节点                                                                                                                                                                                                                                          | boolean                                                                                                                           | false                                   |          | -        |
| canOnlyCheckLeaf     | 多选时是否只能选中叶子节点                                                                                                                                                                                                                                          | boolean                                                                                                                           | false                                   |          | -        |
| checkStrictly        | 父子节点是否选中不关联                                                                                                                                                                                                                                              | boolean                                                                                                                           | false                                   |          | -        |
| listStyle            | 每列列表样式对象                                                                                                                                                                                                                                                    | React.CSSProperties                                                                                                               | -                                       |          | -        |
| listClassName        | 每列列表类名                                                                                                                                                                                                                                                        | string                                                                                                                            | -                                       |          | -        |
| itemRender           | 每列列表项渲染函数<br/><br/>**签名**:<br/>**参数**:<br/>_data_: 数据<br/>_props_: 列表项属性<br/>**返回值**:<br/>列表项内容                                                                                                                                         | (data: CascaderDataItem, props: ItemProps) => React.ReactNode                                                                     | (item: CascaderDataItem) =\> item.label |          | -        |
| loadData             | 异步加载数据函数，source 是原始对象<br/><br/>**签名**:<br/>**参数**:<br/>_data_: 当前点击异步加载的数据<br/>_source_: 当前点击数据，source 是原始对象                                                                                                               | (data: CascaderDataItem, source: CascaderDataItem) => Promise\<unknown>                                                           | -                                       |          | -        |
| immutable            | 是否是不可变数据                                                                                                                                                                                                                                                    | boolean                                                                                                                           | false                                   |          | 1.23.0   |

### CascaderDataItem

```typescript
export type CascaderDataItem = {
    value: string;
    label?: React.ReactNode;
    disabled?: boolean;
    checkboxDisabled?: boolean;
    children?: Array<CascaderDataItem>;
    title?: string;
    [propName: string]: unknown;
};
```

### CascaderDataItemWithPosInfo

```typescript
export type CascaderDataItemWithPosInfo = CascaderDataItem & {
    /**
     * 位置信息
     */
    pos: string;
    _source?: CascaderDataItem;
};
```

### Extra

```typescript
export type Extra = {
    /**
     * 单选时选中的数据的路径
     */
    selectedPath?: Array<CascaderDataItem>;
    /**
     * 多选时当前的操作是选中还是取消选中
     */
    checked?: boolean;
    /**
     * 多选时当前操作的数据
     */
    currentData?: CascaderDataItem;
    /**
     * 多选时所有被选中的数据
     */
    checkedData?: Array<CascaderDataItem>;
    /**
     * 多选时半选的数据
     */
    indeterminateData?: Array<CascaderDataItem>;
};
```

<!-- api-extra-start -->

### dataSource数据结构

```js
const dataSource = [
    {
        value: '2974',
        label: '西安',
        children: [
            { value: '2975', label: '西安市', disabled: true },
            { value: '2976', label: '高陵县', checkboxDisabled: true },
            { value: '2977', label: '蓝田县' },
            { value: '2978', label: '户县' },
            { value: '2979', label: '周至县' },
            { value: '4208', label: '灞桥区' },
            { value: '4209', label: '长安区' },
            { value: '4210', label: '莲湖区' },
            { value: '4211', label: '临潼区' },
            { value: '4212', label: '未央区' },
            { value: '4213', label: '新城区' },
            { value: '4214', label: '阎良区' },
            { value: '4215', label: '雁塔区' },
            { value: '4388', label: '碑林区' },
            { value: '610127', label: '其它区' },
        ],
    },
];
```

数组中 Item 的自定义属性也会被透传到 onChange 函数的 data 参数中。

<!-- api-extra-end -->

## 无障碍键盘操作指南

| 按键        | 说明                                         |
| :---------- | :------------------------------------------- |
| Left Arrow  | 获取同级当前项前一项焦点                     |
| Right Arrow | 获取同级当前项后一项焦点                     |
| Tab         | 进入当前项的子元素，并获取第一个子元素为焦点 |
| Esc         | 返回当前项的父元素并获取焦点                 |
| SPACE       | 选择当前项                                   |


---


## cascader-select

# zh-CN order=11&debug=true

# 无障碍支持

当聚焦在组件上时，通过`aria-labelledby`对组件进行描述。关于键盘操作请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=11

# Accessibility

When the developer presses the Enter key to select an item, the screen reader will reads the selection item, which is described by `aria-labelledby`.
Please refer to `ARIA and KeyBoard` for keyboard operation.


---


## cascader-select

# zh-CN order=0

# 基本使用

展示基本的单选用法。

# en-US order=0

# Basic Usage

Demo the basic single select usage.


---


## cascader-select

# zh-CN order=6

# 选中即发生改变

通过`changeOnSelect`设置是否选中即发生改变,允许只选中父节点，该属性仅在单选模式下有效。

# en-US order=6

# changeOnSelect

Demo whether change on select.


---


## cascader-select

# zh-CN order=8

# 设置父子节点选中是否关联

通过`checkStrictly`设置父子节点是否关联选中状态，仅在多选情况下有效。

# en-US order=8

# Set parent or child nodes to select whether to relate

Demo whether parent and child nodes checked is related.


---


## cascader-select

# zh-CN order=9

# 自定义值渲染

通过`valueRender`自定值渲染。

# en-US order=9

# Custom value render

Custom value render use `valueRender`.


---


## cascader-select

# zh-CN order=10

# 自定义Item样式

可以通过 `displayRender` 来定制单选时展示的结果，可以通过 `listStyle`，`listClassName` 来定制组件宽高。

# en-US order=10

# Customize style

You can use displayRender to customize the results displayed when single select, and you can customize the component width and height by using listStyle and listClassName.


---


## cascader-select

# zh-CN order=4

# 禁用状态

通过 `disabled` 属性设置是否禁用节点，禁用情况下，节点将不响应任何交互；通过 `checkboxDisabled` 属性设置节点是否可以勾选，仅在多选情况下生效。

# en-US order=4

# Basic Usage

Demo the basic single select usage.


---


## cascader-select

# zh-CN order=7

# 异步加载数据

通过`loadData`动态获取数据，`isLeaf`属性用于标志是否是叶子节点。

# en-US order=7

# Loading data asynchronously

Demon loading data asynchronously.


---


## cascader-select

# zh-CN order=4

# 展开触发行为

展示可通过 `expandTriggerType` 来设置不同的展开触发行为，支持 `click` 和 `hover`，默认值为`click`。

# en-US order=4

# Expand trigger type

You can set expand trigger type by setting `expandTriggerType`, support `click` and `hover`, the default is `click`.


---


## cascader-select

# zh-CN order=2

# 默认展开值

通过`defaultExpandedValue`设置默认展开值用法。

# en-US order=2

# Default Expanded Value

Default expanded value.


---


## cascader-select

# zh-CN order=1

# 多选

设置`multiple`为`true`，开启多选，此时节点可勾选。

# en-US order=1

# Multiple select

Demo the basic multiple select usage.


---


## cascader-select

# zh-CN order=5

# 设置是否只能选择叶子项

通过`canOnlyCheckLeaf`属性设置是否仅叶子节点可勾选，仅在多选的时候有效。

# en-US order=5

# Set whether to only select leaf items

Demo whether it can only select leaf items.


---


## cascader-select

# zh-CN order=3

# 搜索

通过设置`showSearch`为`true`，可以开启组件的搜索功能, 通过`filter`属性自定义搜索逻辑。

# en-US order=3

# Search

You can enable search by setting showSearch to true.


---


## cascader-select

# zh-CN order=4&debug=true

# 异步搜索

通过设置`onSearch`，实现异步搜索。

# en-US order=4

# Search

You can enable async search by onSearch prop.


---


## cascader-select

# CascaderSelect

-   category: Components
-   family: DataEntry
-   chinese: 级联选择
-   type: 基本

---

级联选择。

## 何时使用

级联选择由选择器和级联组成。把级联组件以弹层的方式隐藏，多用于表单场景。

## API

### CascaderSelect

继承 Cascader, Select 的部分属性，支持透传给 Cascader 的属性有 dataSource, useVirtual, multiple, canOnlyCheckLeaf,
checkStrictly, resultRender, expandedValue, defaultExpandedValue, expandTriggerType, onExpand, listStyle,
listClassName, loadData, itemRender, immutable。支持透传给 Select 的包括除上面传给 Cascader 和下方单独列出的属性以外的其他全部属性。

| 参数                 | 说明                                                                                                                                           | 类型                                                                                                                                               | 默认值   | 是否必填 | 支持版本 |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------- | -------- |
| size                 | 选择框大小                                                                                                                                     | 'small' \| 'medium' \| 'large'                                                                                                                     | 'medium' |          | -        |
| disabled             | 是否禁用                                                                                                                                       | boolean                                                                                                                                            | false    |          | -        |
| hasArrow             | 是否有下拉箭头                                                                                                                                 | boolean                                                                                                                                            | true     |          | -        |
| hasBorder            | 是否有边框                                                                                                                                     | boolean                                                                                                                                            | true     |          | -        |
| hasClear             | 是否有清除按钮                                                                                                                                 | boolean                                                                                                                                            | false    |          | -        |
| readOnly             | 是否只读，只读模式下可以展开弹层但不能选                                                                                                       | boolean                                                                                                                                            | -        |          | -        |
| defaultValue         | （非受控）默认值                                                                                                                               | string \| Array\<string>                                                                                                                           | -        |          | -        |
| value                | （受控）当前值                                                                                                                                 | string \| Array\<string>                                                                                                                           | -        |          | -        |
| onChange             | 选中值改变时触发的回调函数                                                                                                                     | (<br/> value: string \| Array\<string> \| null,<br/> data: CascaderDataItem \| Array\<CascaderDataItem> \| null,<br/> extra?: Extra<br/> ) => void | -        |          | -        |
| changeOnSelect       | 是否选中即发生改变，该属性仅在单选模式下有效                                                                                                   | boolean                                                                                                                                            | false    |          | -        |
| displayRender        | 选择框单选时展示结果的自定义渲染函数                                                                                                           | (<br/> label: Array\<React.ReactNode>,<br/> data: CascaderSelectDataItem<br/> ) => React.ReactNode                                                 | -        |          | -        |
| showSearch           | 是否显示搜索框                                                                                                                                 | boolean                                                                                                                                            | false    |          | -        |
| filter               | 自定义搜索函数                                                                                                                                 | (searchValue: string, path: CascaderSelectDataItem[]) => boolean                                                                                   | -        |          | -        |
| onSearch             | 当搜索框值变化时回调                                                                                                                           | (value: string) => void                                                                                                                            | -        |          | 1.23     |
| resultAutoWidth      | 搜索结果列表是否和选择框等宽                                                                                                                   | boolean                                                                                                                                            | true     |          | -        |
| notFoundContent      | 无数据时显示内容                                                                                                                               | React.ReactNode                                                                                                                                    | -        |          | -        |
| header               | 自定义下拉框头部                                                                                                                               | React.ReactNode                                                                                                                                    | -        |          | -        |
| footer               | 自定义下拉框底部                                                                                                                               | React.ReactNode                                                                                                                                    | -        |          | -        |
| defaultVisible       | 初始下拉框是否显示                                                                                                                             | boolean                                                                                                                                            | false    |          | -        |
| visible              | 当前下拉框是否显示                                                                                                                             | boolean                                                                                                                                            | -        |          | -        |
| onVisibleChange      | 下拉框显示或关闭时触发事件的回调函数                                                                                                           | (visible: boolean, type?: CascaderSelectVisibleChangeType) => void                                                                                 | -        |          | -        |
| popupProps           | 透传到 Popup 的属性对象                                                                                                                        | React.ComponentPropsWithRef\<typeof Popup>                                                                                                         | -        |          | -        |
| isPreview            | 是否为预览态                                                                                                                                   | boolean                                                                                                                                            | false    |          | -        |
| renderPreview        | 自定义预览态                                                                                                                                   | (<br/> value: CascaderSelectDataItem \| CascaderSelectDataItem[],<br/> props: CascaderSelectProps<br/> ) => React.ReactNode                        | -        |          | -        |
| menuProps            | 透传到 Cascader 的属性对象；focusedKey、onItemFocus、className、style、focusable、isSelectIconRight 传入无效，其中 onBlur 在 filter 下传入无效 | Omit\<CascaderProps, 'onSelect' \| 'onChange'>                                                                                                     | -        |          | -        |
| autoClearSearchValue | 是否在选中项后清空搜索框，只在 multiple 为 true 时有效                                                                                         | boolean                                                                                                                                            | false    |          | -        |

<!-- api-extra-start -->

### dataSource数据结构

```js
const dataSource = [
    {
        value: '2974',
        label: '西安',
        children: [
            { value: '2975', label: '西安市', disabled: true },
            { value: '2976', label: '高陵县', checkboxDisabled: true },
            { value: '2977', label: '蓝田县' },
            { value: '2978', label: '户县' },
            { value: '2979', label: '周至县' },
            { value: '4208', label: '灞桥区' },
            { value: '4209', label: '长安区' },
            { value: '4210', label: '莲湖区' },
            { value: '4211', label: '临潼区' },
            { value: '4212', label: '未央区' },
            { value: '4213', label: '新城区' },
            { value: '4214', label: '阎良区' },
            { value: '4215', label: '雁塔区' },
            { value: '4388', label: '碑林区' },
            { value: '610127', label: '其它区' },
        ],
    },
];
```

数组中 Item 的自定义属性也会被透传到 onChange 函数的 data 参数中。

<!-- api-extra-end -->

## 无障碍键盘操作指南

| 按键        | 说明                                         |
| :---------- | :------------------------------------------- |
| Up Arrow    | 获取同级当前项前一项焦点                     |
| Down Arrow  | 获取同级当前项后一项焦点                     |
| Left Arrow  | 进入当前项的子元素，并获取第一个子元素为焦点 |
| Right Arrow | 返回当前项的父元素并获取焦点                 |
| Enter       | 打开目录或选择当前项                         |
| Esc         | 关闭目录                                     |
| SPACE       | 选择当前项                                   |


---


## checkbox

# zh-CN order=8

# 无障碍支持

通过`aria-label`对`Checkbox`组件进行描述。关于键盘操作请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=8

# Accessibility

Describe the `Checkbox` component with `aria-label`.Please refer to `ARIA and KeyBoard` for keyboard operation.


---


## checkbox

# zh-CN order=7

# 全选

使用受控`Checkbox.Group`与中间状态，实现全选功能。

# en-US order=7

# All check

All checked state of `Checkbox`.


---


## checkbox

# zh-CN order=0

# 基本

使用 `Checkbox` 渲染的基本组件。

# en-US order=0

# Basic Usage

Basic components rendered using `Checkbox`.


---


## checkbox

# zh-CN order=6

# 受控组件

使用 `Checkbox.Group` 渲染的组，通过设置 `value` 属性可以让组件变成[受控组件](https://facebook.github.io/react/docs/forms.html#controlled-components)。

# en-US order=6

# Controlled Component

Groups rendered using `Checkbox.Group` can make the component a [controlled component] by setting the `value` property (https://facebook.github.io/react/docs/forms.html#controlled-components).


---


## checkbox

# zh-CN order=5

# 传入数组配置

通过配置 `dataSource` 参数来渲染单选框分组，数组中对象元素支持配置Checkbox属性。

# en-US order=5

# DataSource Usage

Groups that are rendered using `CheckboxGroup` can set the component using `dataSource`.


---


## checkbox

# zh-CN order=1

# 禁用状态

`Checkbox`禁用状态。

# en-US order=1

# Disabled

Disabled state of `Checkbox`.


---


## checkbox

# zh-CN order=4

# Checkbox组

使用 `<Checkbox.Group>` 渲染 `<Checkbox>` 分组。

# en-US order=4

# Group Checkbox

Grouping `<Checkbox>` with `<Checkbox.Group>`.


---


## checkbox

# zh-CN order=2

# 中间状态

通过使用 `indeterminate` 来渲染[中间状态](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)的组件。

# en-US order=2

# Intermediate State Component

Render the components of [Intermediate State] (https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox) by using `indeterminate`.


---


## checkbox

# zh-CN order=3

# 预览状态

`Checkbox`预览状态。

# en-US order=3

# isPreview

Preview state of `Checkbox`.


---


## checkbox

# zh-CN order=9&debug=true

# 非受控组件

使用 `CheckboxGroup` 渲染的组，通过设置 `defaultValue` 属性可以让组件变成[非受控组件](https://facebook.github.io/react/docs/forms.html#uncontrolled-components)。

# en-US order=9&debug=true

# Uncontrolled Component

Groups rendered with `CheckboxGroup` can be made to become [uncontrolled components] by setting the `defaultValue` property (https://facebook.github.io/react/docs/forms.html#uncontrolled-components).


---


## checkbox

# Checkbox

-   category: Components
-   family: DataEntry
-   chinese: 复选按钮
-   type: 表单

---

多选框。

## 何时使用

-   在一组可选项中进行多项选择时；
-   单独使用可以表示两种状态之间的切换，和 switch 类似。区别在于切换 switch 会直接触发状态改变，而 checkbox 一般用于状态标记，需要和提交操作配合。

## API

### Checkbox

| 参数                 | 说明                                                                                                                                         | 类型                                                                 | 默认值 | 是否必填 | 支持版本 |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- | ------ | -------- | -------- |
| className            | 自定义类名                                                                                                                                   | string                                                               | -      |          | -        |
| id                   | checkbox id, 挂载在 input 上                                                                                                                 | string                                                               | -      |          | -        |
| style                | 自定义内联样式                                                                                                                               | React.CSSProperties                                                  | -      |          | -        |
| checked              | 选中状态                                                                                                                                     | boolean                                                              | -      |          | -        |
| value                | checkbox 的 value                                                                                                                            | ValueItem                                                            | -      |          | -        |
| name                 | name                                                                                                                                         | string                                                               | -      |          | -        |
| defaultChecked       | 默认选中状态                                                                                                                                 | boolean                                                              | false  |          | -        |
| disabled             | 禁用                                                                                                                                         | boolean                                                              | -      |          | -        |
| label                | 通过属性配置 label，                                                                                                                         | React.ReactNode                                                      | -      |          | -        |
| indeterminate        | Checkbox 的中间状态，只会影响到 Checkbox 的样式，并不影响其 checked 属性                                                                     | boolean                                                              | -      |          | -        |
| defaultIndeterminate | Checkbox 的默认中间态，只会影响到 Checkbox 的样式，并不影响其 checked 属性                                                                   | boolean                                                              | false  |          | -        |
| onChange             | 状态变化时触发的事件                                                                                                                         | (checked: boolean, e: React.ChangeEvent\<HTMLInputElement>) => void  | -      |          | -        |
| onMouseEnter         | 鼠标进入 enter 事件                                                                                                                          | (e: React.MouseEvent\<HTMLInputElement \| HTMLLabelElement>) => void | -      |          | -        |
| onMouseLeave         | 鼠标离开 Leave 事件                                                                                                                          | (e: React.MouseEvent\<HTMLInputElement \| HTMLLabelElement>) => void | -      |          | -        |
| isPreview            | 是否为预览态                                                                                                                                 | boolean                                                              | false  |          | 1.19     |
| renderPreview        | 预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_checked_: 是否选中<br/>_props_: 所有传入的参数<br/>**返回值**:<br/>定制渲染内容 | (checked: boolean, props: CheckboxProps) => React.ReactNode          | -      |          | 1.19     |

### Checkbox.Group

| 参数          | 说明                                                                                                                                                                       | 类型                                                                                                                                                     | 默认值 | 是否必填 | 支持版本 |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | -------- | -------- |
| className     | 自定义类名                                                                                                                                                                 | string                                                                                                                                                   | -      |          | -        |
| style         | 自定义内联样式                                                                                                                                                             | React.CSSProperties                                                                                                                                      | -      |          | -        |
| disabled      | 整体禁用                                                                                                                                                                   | boolean                                                                                                                                                  | -      |          | -        |
| dataSource    | 可选项列表                                                                                                                                                                 | Array\<ValueItem> \| Array\<CheckboxData>                                                                                                                | -      |          | -        |
| value         | 被选中的值列表                                                                                                                                                             | ValueItem[] \| ValueItem                                                                                                                                 | -      |          | -        |
| defaultValue  | 默认被选中的值列表                                                                                                                                                         | ValueItem[] \| ValueItem                                                                                                                                 | -      |          | -        |
| name          | name                                                                                                                                                                       | string                                                                                                                                                   | -      |          | -        |
| children      | 通过子元素方式设置内部 checkbox                                                                                                                                            | React.ReactNode                                                                                                                                          | -      |          | -        |
| onChange      | 选中值改变时的事件                                                                                                                                                         | (value: ValueItem[], e: React.ChangeEvent\<HTMLInputElement>) => void                                                                                    | -      |          | -        |
| direction     | 子项目的排列方式                                                                                                                                                           | 'hoz' \| 'ver'                                                                                                                                           | -      |          | -        |
| itemDirection | [废弃] 子项目的排列方式                                                                                                                                                    | 'hoz' \| 'ver'                                                                                                                                           | -      |          | -        |
| isPreview     | 是否为预览态                                                                                                                                                               | boolean                                                                                                                                                  | -      |          | 1.19     |
| renderPreview | 预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_previewed_: 预览值 [\{label: '', value:''\},...]<br/>_props_: 所有传入的参数<br/>**返回值**:<br/>定制渲染内容 | (<br/> previewed: {<br/> label: string \| React.ReactNode;<br/> value: string \| React.ReactNode;<br/> }[],<br/> props: object<br/> ) => React.ReactNode | -      |          | 1.19     |

### ValueItem

```typescript
export type ValueItem = string | number | boolean;
```

### CheckboxData

```typescript
export type CheckboxData = {
    value: ValueItem;
    label?: React.ReactNode;
    disabled?: boolean;
    [propName: string]: unknown;
};
```

## 无障碍键盘操作指南

| 按键  | 说明             |
| :---- | :--------------- |
| SPACE | 选择或取消当前项 |


---


## collapse

# zh-CN order=6

# 无障碍支持

组件内置了部分支持无障碍, 但是额外需要开发者手动事情才能完整支持无障碍: 给Collapse传入一个id, 组件会根据Collapse的id自动给每一个Panel生成Id。如果你想指定Panel的Id也可以, 给某个Panel传入Id属性,就会覆盖根据CollapseId生成的Id。

# en-US order=6

# Accessibility

To Support accessibility, you shoud assign an id prop to Collapse and it will generate id for Panels. or you can assign an id prop to Panel to overwrite generated id.


---


## collapse

# zh-CN order=2

# 手风琴

手风琴单例模式，每次只打开一个Panel。

# en-US order=2

# Accordion

Accordion mode, you can only open at most one panel.


---


## collapse

# zh-CN order=0

# 基本

可以同时展开多个面板

# en-US order=0

# Basic Usage

can open mutiple panel


---


## collapse

# zh-CN order=1

# 数据源

直接使用 dataSource 展示

# en-US order=1

# Data Source

use dataSource to display


---


## collapse

# zh-CN order=4

# 全部禁用

disabled 禁用全部

# en-US order=4

# disable

use disabled to disable all


---


## collapse

# zh-CN order=5

# 展开事件

1. 所有的Panel不传入 Key ,自动分配 key 为index
2. 任意一个 Panel 手动传入 key , 则不分配 key .
3. 建议所有的 Panel 都传入 key 或者都不传 key

# en-US order=5

# Expaned Event

1. if all Panels have no key, key will be allocated to index.
2. if some Panels have key, key won't be allocated.
3. Strongly recommand all Panels have no key or every Panel has a key.


---


## collapse

# zh-CN order=3

# 面板嵌套

嵌套折叠面板。

# en-US order=3

# Nested Collapse

Nested Collapse


---


## collapse

# Collapse

-   category: Components
-   family: DataDisplay
-   chinese: 折叠面板
-   type: 布局

---

折叠面板组件。

## 何时使用

-   对复杂区域进行分组和隐藏，保持页面的整洁。

-   手风琴 是一种特殊的折叠面板，只允许单个内容区域展开。

## API

### Collapse

| 参数                | 说明                         | 类型                                         | 默认值 | 是否必填 |
| ------------------- | ---------------------------- | -------------------------------------------- | ------ | -------- |
| dataSource          | 使用数据模型构建             | Array\<DataItem>                             | -      |          |
| defaultExpandedKeys | 默认展开 keys                | KeyType[]                                    | -      |          |
| expandedKeys        | 受控展开 keys                | KeyType[]                                    | -      |          |
| onExpand            | 展开状态发升变化时候的回调   | (expandedKeys: KeyType \| KeyType[]) => void | -      |          |
| disabled            | 所有禁用                     | boolean                                      | -      |          |
| accordion           | 手风琴模式，一次只能打开一个 | boolean                                      | false  |          |

### Collapse.Panel

| 参数       | 说明             | 类型                                                                                               | 默认值 | 是否必填 |
| ---------- | ---------------- | -------------------------------------------------------------------------------------------------- | ------ | -------- |
| disabled   | 是否禁止用户操作 | boolean                                                                                            | -      |          |
| title      | 标题             | React.ReactNode                                                                                    | -      |          |
| isExpanded | 是否展开         | boolean                                                                                            | false  |          |
| onClick    | 点击回调函数     | \| ((e: React.MouseEvent\<HTMLElement> \| React.KeyboardEvent\<HTMLElement>) => void)<br/> \| null | -      |          |

### KeyType

```typescript
export type KeyType = string | number;
```

### DataItem

```typescript
export type DataItem = {
    id?: string;
    title?: React.ReactNode;
    content?: React.ReactNode;
    disabled?: boolean;
    key?: KeyType;
    onClick?: (key: KeyType) => void;
    [propName: string]: unknown;
};
```

## 无障碍键盘操作指南

| 按键  | 说明                        |
| :---- | :-------------------------- |
| Tab   | 切换到下一个 collapse panel |
| Space | 切换 collapse 的折叠状态    |


---


## config-provider

# zh-CN order=1

# 基本

最简单的用法，展示 ConfigProvider 是如何工作的。

# en-US order=1

# Basic

The simplest usage, demo how ConfigProvider works.


---


## config-provider

# zh-CN order=2

# 支持国际化的组件

展示目前 Next 组件中支持国际化的组件。

# en-US order=2

# Components that support internationalization

Show the components that support internationalization in the current Next components.


---


## config-provider

# zh-CN order=4

# 使用 Consumer 组件读取上下文中的数据

使用 `<Consumer>` 可以方便地读取 `<ConfigProvider>` 中上下文的数据

# en-US order=4

# Basic

`<Consumer>` can be to read context state of `<ConfigProvider>` with easly and highly customized


---


## config-provider

# zh-CN order=5

# ErrorBoundary 捕获错误

使用 `<ErrorBoundary>` 可以避免由于局部区域的错误，所引起的页面白屏。

# en-US order=5

# Basic

`<ErrorBoundary>` can be used to avoid blank screen caused by local errors


---


## config-provider

# zh-CN order=6

# 交互能力可配置

通过 `defaultPropsConfig` 可以配置一些 API 的默认值

# en-US order=6

# Interactive

Set defaultProps via `defaultPropsConfig`


---


## config-provider

# zh-CN order=0

# 国际化

展示如何配合 ConfigProvider 实现具有国际化能力的组件。

# en-US order=0

# Internationalization

Demo how to use ConfigProvider to implement components with international capabilities.


---


## config-provider

# zh-CN order=4

# 组件的RTL

组件RTL样式展示(目前部分支持)

# en-US order=4

# Components with rtl

Show components with RTL(Partial supported currently).


---


## config-provider

# ConfigProvider

-   category: Components
-   family: Util
-   chinese: 全局配置 Next 组件
-   type: 基本

---

配置Provider。

## 何时使用

-   修改组件类名前缀，Next 组件类名的默认前缀都是 'next-'，如 'next-btn'，你可能在以下两种情况下想改变这个默认前缀：
    -   自定义组件品牌，如 'my-btn'，'my-select'
    -   一个页面中同时引入两个主题，防止相同类名样式互相覆盖
-   实现多语言文案切换
-   开启 Pure Render 模式，提高性能，注意同时可能会带来副作用

## 如何使用

### 指定多语言文案

通过 `<ConfigProvider locale={localeObj}>` 传入语言包，以支持多语言。目前 Fusion 内置的 locale 库支持中英繁日四种语言，覆盖各组件的简单词汇，例如：确定、取消、展开、收起、下一页等， 简单词汇映射表可参考 <https://unpkg.com/@alifd/next/lib/locale/>

(ConfigProvider 提供简单组件简单词汇国际化能力，由于日期时间的国际化较为特殊，例如中国的日历是从周一到周日，美国的日历是从周日到周六等，时间相关的组件如DatePicker等需要国际化，请查看相应组件文档。)

可通过两种方式设置多语言文案，两种方式接收的对象格式略有不同:

-   1.设置组件自身 locale 属性

```jsx
{
    key1: value1,
    key2: value2
}
```

-   2.ConfigProvider 的 locale 属性 (推荐)

```jsx
{
    component1: {
        key1: value1,
        key2: value2
    },
    component2: {
        key1: value1,
        key2: value2
    }
}
```

以 locale 为例（其他属性如prefix等，同理），被 ConfigProvider.config() 设置过的组件（基础组件默认都被设置过），生效的 locale 优先级顺序为:

props 方式的 locale > 最近 ConfigProvider 的 locale > 更远父级 ConfigProvider 的 locale

以下面伪代码为例，即：CLocale > BLocale > ALocale

```jsx
<ConfigProvider locale={ALocale}>
    <ConfigProvider locale={BLocale}>
        <Button locale={CLocale} />
    </ConfigProvider>
</ConfigProvider>
```

(注： 由于`Dialog.show()` `Message.show()` 等函数式方法的特殊性，他们的将默认读取页面上的root context。当页面上有多个包含`<ConfigProvider/>` 的 `ReactDOM.render()`方法调用时，由第一个渲染的决定root context)

```jsx
import { ConfigProvider, DatePicker } from '@alifd/next';

const localeDatePicker = {
    placeholder: 'localeDatePicker placeholder',
};

const localeGlobal = {
    DatePicker: {
        placeholder: 'localeGlobal placeholder',
    },
};

class App extends React.Component {
    render() {
        return (
            <div>
                <ConfigProvider locale={localeGlobal}>
                    <DatePicker /> should be 'localeGlobal placeholder'
                </ConfigProvider>
                <br />
                <br />
                <ConfigProvider locale={localeGlobal}>
                    <DatePicker locale={localeDatePicker} /> should be 'localeDatePicker
                    placeholder'
                </ConfigProvider>
            </div>
        );
    }
}
```

根据引入组件库方式的不同(CDN直接引用、作为依赖引用)，使用语言包的方式略有差异，具体见如下代码：

```jsx
import { ConfigProvider, DatePicker } from '@alifd/next';
import enUS from '@alifd/next/lib/locale/en-us';
// import zhCN from '@alifd/next/lib/locale/zh-cn';
// import zhHK from '@alifd/next/lib/locale/zh-hk';
// import zhTW from '@alifd/next/lib/locale/zh-tw';
// import jaJP from '@alifd/next/lib/locale/ja-jp';

// 如果应用中直接引入的是 cdn 上的 next-with-locales.js 文件
// 需要按照下面的方式引入国际化文案文件
// const { ConfigProvider, DatePicker, locales } = window.Next;
// const enUS = locales['en-us'];

class App extends React.Component {
    render() {
        return (
            <ConfigProvider locale={enUS}>
                <DatePicker />
            </ConfigProvider>
        );
    }
}
```

如果内置的 locale 库不满足你的需求(比如想支持法语、德语、西班牙语)，你也可以参考 <https://unpkg.com/@alifd/next/lib/locale/> 来自定义语言包，按照如下格式传入给 locale 即可：

```jsx
{
    DatePicker: {
        datePlaceholder: 'Select date',
        monthPlaceholder: 'Select month',
        yearPlaceholder: 'Select year',
        rangeStartPlaceholder: 'Start date',
        rangeEndPlaceholder: 'End date',
        ok: 'OK',
        clear: 'Clear'
    },
    Dialog: {
        // ...
    },
    // ...
}
```

### 修改组件类名前缀

1.  为你的应用包裹 ConfigProvider，并设置相应的 prefix

    entry.jsx

    ```jsx
    class App extends React.Component {
        render() {
            return (
                <ConfigProvider prefix="my-">
                    <div>
                        <Input />
                        <Button>Submit</Button>
                    </div>
                </ConfigProvider>
            );
        }
    }
    ```

2.  scss 入口文件中在引入主题 scss 文件前，设置相应的 `$css-prefix`

    entry.scss

    ```scss
    $css-prefix: 'my-';
    @import '~@alifd/theme-xxx/index.scss';
    ```

### 开启 Pure Render

```jsx
import { ConfigProvider, DatePicker } from '@alifd/next';

class App extends React.Component {
    render() {
        return (
            <ConfigProvider pure>
                <DatePicker />
            </ConfigProvider>
        );
    }
}
```

### 全局 ConfigProvider

```jsx
import { ConfigProvider } from '@alifd/next';
import locale from './locale';

const { config } = ConfigProvider;

class Component extends React.Component {
    static propTypes = {
        prefix: PropTypes.string,
        locale: PropTypes.object,
        pure: PropTypes.bool,
    };

    static defaultProps = {
        prefix: 'next-',
        locale: locale,
        pure: false,
    };

    render() {
        const { prefix, locale, pure } = this.props;
        // ...
    }
}

export default config(Component);
```

## API

### ConfigProvider

| 参数               | 说明                                                               | 类型                    | 默认值 | 是否必填 |
| ------------------ | ------------------------------------------------------------------ | ----------------------- | ------ | -------- |
| prefix             | 样式类名的品牌前缀                                                 | string                  | -      |          |
| pure               | 是否开启 Pure Render 模式，会提高性能，但是也会带来副作用          | boolean                 | -      |          |
| device             | 设备类型，针对不同的设备类型组件做出对应的响应式变化               | DeviceType              | -      |          |
| rtl                | 是否开启 rtl 模式                                                  | boolean                 | -      |          |
| errorBoundary      | 是否开启错误捕捉                                                   | ErrorBoundaryType       | false  |          |
| warning            | 是否在开发模式下显示组件属性被废弃的 warning 提示                  | boolean                 | true   |          |
| locale             | 各组件的国际化文案对象，属性为组件的 displayName                   | Partial\<Locale>        | -      |          |
| popupContainer     | 指定浮层渲染的父节点，可以为节点 id 的字符串，也可以返回节点的函数 | PopupContainerType      | -      |          |
| children           | 组件树                                                             | React.ReactNode         | -      |          |
| defaultPropsConfig | 各组件 API 的默认配置                                              | Record\<string, object> | -      |          |

### DeviceType

```typescript
export type DeviceType = 'tablet' | 'desktop' | 'phone';
```

### PopupContainerType

```typescript
export type PopupContainerType = string | HTMLElement | ((target: HTMLElement) => HTMLElement);
```

<!-- api-extra-start -->

### ConfigProvider.config(Component)

传入组件，生成受 ConfigProvider 控制的 HOC 组件，如果组件没有声明 shouldComponentUpdate 方法，会添加如下 shouldComponentUpdate 方法以支持 ConfigProvider 的 pure 属性

```jsx
Component.prototype.shouldComponentUpdate = function shouldComponentUpdate(nextProps, nextState) {
    if (this.props.pure) {
        return !shallowEqual(this.props, nextProps) || !shallowEqual(this.state, nextState);
    }

    return true;
};
```

### ConfigProvider.getContextProps(props, displayName)

传入组件的 props 和 displayName，得到和 childContext 计算过的包含有 preifx/locale/pure 的对象，一般用于通过静态方法生成脱离组件树的组件。

### ConfigProvider.getContext()

通过该方法可以获取到 ConfigProvider 的上下文，格式如下。若有多层级 ConfigProvider 嵌套，会返回第一次注册时所设置的内容。

```jsx
{
    prefix: nextPrefix,
    locale: nextLocale,
    pure: nextPure,
    warning: nextWarning
}
```

### ConfigProvider.initLocales(locales)

配置所有语言包, 可配合 `ConfigProvider.setLanguage` 方法，确定组件使用的语言包。

```jsx
ConfigProvider.initLocales({
    'zh-cn': {},
    'en-us': {},
});
```

### ConfigProvider.setLanguage(language)

设置语言，参数 `language` 需要能在 `ConfigProvider.initLocales` 方法传入的参数的 key 中找到， 默认为 `zh-cn`

```jsx
ConfigProvider.setLanguage('zh-cn');
```

### ConfigProvider.setLocale(locale)

直接设置语言包

```jsx
// 相当于 同时用ConfigProvider.initLocales 和 ConfigProvider.setLanguage
ConfigProvider.setLocale({
    DatePicker: {},
    Dialog: {},
});
```

### ConfigProvider.setDirection(dir)

设置组件展示方向，当传入 `rtl`时，会在组件的根DOM节点加上 `dir="rtl"`，同时组件展示rtl视觉。可用于阿拉伯等阅读顺序从右到左的国家。

```jsx
ConfigProvider.setDirection('rtl');
```

### ConfigProvider.getLocale()

获取当前的语言包

### ConfigProvider.getLanguage()

获取当前设定的语言

### ConfigProvider.getDirection()

获取当前设定的方向

<!-- api-extra-end -->

## FAQ

### 如何减小应用中 webpack 打包 moment 体积？

Next 1.x 中将 moment 作为自己的 peerDependencies 而非 dependencies，所以用户需要自己在应用中引入 moment 的 cdn 文件 moment-with-locales.js 或者本地安装 moment 打包进自己的应用。对于后者，由于 moment 在引入 locale 文件时存在这样的代码：`require('./locale/' + name)`，如果用 webpack 构建，会打包进所有的 [locale 文件](https://github.com/moment/moment/tree/develop/locale)，增加构建后文件的体积，目前社区比较主流的解决方案有以下两种：

```jsx
const webpack = require('webpack');

module.exports = {
    // ...
    plugins: [
        // 打包指定需要的语言文件
        new webpack.ContextReplacementPlugin(/moment[\/\\]locale$/, /zh-cn|ja/),
        // 只打包有过引用的语言文件，应用中需要添加如：`import 'moment/locale/zh-cn';`
        // new webpack.IgnorePlugin(/^\.\/locale$/, /moment$/)
    ],
};
```

### 如何为自定义组件添加 displayName？

ConfigProvider 获取组件对应的多语言文案，是通过组件的 displayName 或者 name 获取的，但是压缩混淆的过程中有可能会修改函数的 name，因此如果想支持在 ConfigProvider 下实现切换多语言切换，请为组件如下手动添加 displayName:

```jsx
class CustomComponent extends React.Component {
    static displayName = 'CustomComponent';
    // ...
}
```

或者使用 `babel-plugin-transform-react-es6-displayname` 自动在编译期间添加 displayname。

### 如何获取 HOC 组件内部组件的引用？

由于 HOC 本身的限制，我们不能直接像下面代码那样获取内部组件的引用，从而调用它的一些内部方法：

```jsx
class App extends React.Component {
    componentDidMount() {
        // 报错
        this.refs.hoc.someMethod();
    }

    render() {
        return <HOC ref="hoc" />;
    }
}
```

为了解决这个问题，我们为调用 config 方法生成的 HOC 组件添加了 getInstance 方法，你可以如下调用：

```jsx
class App extends React.Component {
    componentDidMount() {
        this.refs.hoc.getInstance().someMethod();
    }

    render() {
        return <HOC ref="hoc" />;
    }
}
```


---


## core

# Next - Core

## 简介

### 职责

DPL 中 UED 设计体系与前端 UI 体系的核心接口层，负责将 UED 设计体系中用到的所有原子样式 (参考原子设计) 转化为前端的 CSS 样式声明，以实现设计体系 (类似品牌色、文本色、标题文本等在常见业务中的设计场景) 的模式化，通过此模式 (原子样式变量)，即可配置多种多样不同色系但设计合理的 UI 组件。

在各个 UI 组件中，需要使用原子样式变量构成组件变量，组件变量是各个 UI 组件中使用的变量，而组件变量中使用的原子样式一定来自于 **core**，不可独自定义。

此变量抽象可作为设计的原子样式抽象与前端的基础样式抽象的规范约定。

### 能力

为 Next 的所有 UI 组件提供全局基础样式的变量定义，包括颜色、原角、文本、边线、阴影、动画，以及其他全局变量定义等；全局 Mixins, Functions；以及浏览器基础样式重置和全站文本样式声明。

### 约定

所有 UI 组件必须引用 `@alifd/next-core` 作为全局默认的变量使用，且定义方式，书写规范也必须和 core 保持一致。不允许有其他全局公共变量对 `@alifd/next-core` 覆写。

### 使用

```
npm install @alifd/next-core --save
```

index.scss

```scss
@import '~@alifd/next-core/lib/index-noreset.scss';
```


---


## date-picker

# zh-CN order=13

# 无障碍支持

支持手动输入或键盘操作，请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=13

# Accessibility

Support manual input or keyboard operation,Please refer to `ARIA and KeyBoard`.


---


## date-picker

# zh-CN order=0

# 基本用法

最基本的用法。可以通过 `onChange` 监听选中值的变化。

# en-US order=0

# Basic

A basic usage case.


---


## date-picker

# zh-CN order=5&debug=true

# 自定义日期范围选择

如果默认的 RangePicker 在交互上无法满足您的使用需求，还可以基于 DatePicker 封装实现类似的功能。
例如，示例中的日期选择可以自由的更改开始或结束日期，而不必每次选择时重置日期。

# en-US order=5&debug=true

# Custom RangePicker

Create your own RangePicker with two DatePickers.


---


## date-picker

# zh-CN order=1

# 提供默认值

可以通过 `defaultValue` 属性为日期选择器提供初值，所提供的初值必须为 `moment` 对象。

# en-US order=1

# Default value

Setting default value by passing `defaultValue`.


---


## date-picker

# zh-CN order=6

# 面板的默认展现日期

可以通过 `defaultVisibleMonth` 或 `defaultVisibleYear` 属性可以修改面板的默认展现日期。

# en-US order=6

# Default visible month

Change default visible month by setting `defaultVisibleMonth` or `defaultVisibleYear`.


---


## date-picker

# zh-CN order=8

# 禁用状态

当开启 `disabled` 属性时，选择框处于完全禁用状态。

# en-US order=8

# Disabled

Disable the picker.


---


## date-picker

# zh-CN order=4

# 禁止选择某些日期

可以通过 `disabledDate` 属性来禁止用户选择或输入某些特定日期。

# en-US order=4

# Disable dates

Disable date cells by `disabledDate`.


---


## date-picker

# zh-CN order=12

# 与 Field 结合

与 Field 结合使用，简单示范自定义返回值

# en-US order=12

# Field

Use case with Field.


---


## date-picker

# zh-CN order=10

# 自定义面板页脚

可以通过 `footerRender` 自定义对面板页脚的定制。

# en-US order=10

# Footer

Passing custom footer with `footerRender`.


---


## date-picker

# zh-CN order=2

# 日期格式

通过 `format` 属性可以约束日期选择器的日期格式，该格式同时会限定用户的输入格式。

# en-US order=2

# Format

Using attribute `format` to change the displayed dates, it will be also used to check user inputs.


---


## date-picker

# zh-CN order=9

# 自定义日期选择器弹层

组件对外透出了 `visible`, `defaultVisible`, `onVisibleChange`, `popupTriggerType`, `popupAlign`, `popupContainer`, `popupStyle`, `popupClassName` 等属性用于直接定制弹层。此外，如果这些属性仍然无法满足需求，可以通过 `popupProps` 进行透传。

# en-US order=9

# Custom popup

Custom popup behaviors.


---


## date-picker

# zh-CN order=3

# 日期时间选择

如果需要同时选择时间，可以通过 `showTime` 属性开启，`showTime` 支持传入 `TimePickerPanel` 的属性，例如 `format`, `defaultValue` 等。

# en-US order=3

# With time

Enable `showTime` to create a DatePicker/RangePicker with time.


---


## date-picker

# zh-CN order=11

# 不同尺寸

通过 `size` 属性可以改变 Input 组件的尺寸，默认为 `medium`。

# en-US order=11

# Size

Change size by attribute `size`.


---


## date-picker

# DatePicker

-   category: Components
-   family: DataEntry
-   chinese: 日期选择框
-   type: 表单

---

日期组件。

## 何时使用

输入或选择日期的控件。当用户需要输入一个日期，可以点击标准输入框，弹出日期面板进行选择。

## 如何使用

### 日期选择模式

DatePicker/RangePicker 在交互上增加了**操作焦点**的设置，意味着，如果某个输入框处于 focus 态，那么当前选择的日期将会作用于该输入框对应的日期。

如上图所示，带时间的 RangePicker 有 4 个输入焦点，分别为开始日期、开始时间、结束日期、结束时间。当用户激活某个输入框时，此时下拉选择的日期将会作用域该输入框。同时设置了如下两个规则：

1.  已选定日期范围后，当焦点在开始日期时，如果即将选择的日期大于结束日期，将会重设开始日期。
2.  已选定日期范围后，当焦点在结束日期时，如果即将选择的日期小于开始日期，将会重设开始日期。

### 日期值的多语言

由于 Calendar 组件内部使用 moment 对象来设置日期（请使用最新版 moment），部分 Locale 读取自 moment，因此用户需要在外部使用时[正确的设置 moment 的 locale](http://momentjs.cn/docs/#/i18n/changing-locale/) 。

Q: 文档站点上看是中式日历，为什么我本地却是美式日历呢？如何进行多语言适配？<br/>
A: 日期的多语言情况比较复杂，涉及到年、月、日、星期、阅读习惯等多方面 (美式从周日到周六，中式从周一到周日)，因此我们借助了成熟的时间库 moment.js 来进行日期的多语言处理。
moment.js 默认支持美式表达，如需中文等其他语言，请引入 moment-with-locales.js 语言包。

```jsx
import moment from 'moment';

moment.locale('zh-cn');
```

此外，当改变 moment 的全局 locale 时并不会修改之前的已有实例，例如：

```jsx
moment.locale('fr');
const m = moment(1316116057189);
m.fromNow(); // il y a une heure

moment.locale('en');
m.fromNow(); // il y a une heure
moment(1316116057189).fromNow(); // an hour ago
```

除了全局设置 moment 的多语言，还可以只对某个 moment 实例设置多语言。比如：

```jsx
const value = moment();
value.locale('fr'); // set this instance to use French
```

### Moment 对象和字符串

DatePicker 默认情况下接收和返回的数据类型都是 Moment 对象。为了便于用户的使用，DatePikcer 还支持直接传入字符串（组件内部仍然会格式化为 Moment 对象）。使用方法如下：

标准非受控

```jsx
<DatePicker onChange={val => console.log(val)} />
// select 2019-01-23
// >> MomentObject

<DatePicker defaultValue={moment()} onChange={val => console.log(val)} />
// select 2019-01-23
// >> MomentObject

<DatePicker defaultValue="2018-01-23" onChange={val => console.log(val)} />
// select 2019-01-23
// >> "2019-01-23"

<DatePicker defaultValue={moment(1581938105000)} onChange={val => console.log(val)} />
// select 2020-02-17
// >> "2020-02-17"
```

标准受控

```jsx
<DatePicker value={moment()} onChange={val => console.log(val)} />
// setProps({ value: moment().add(1, 'months') })
// >> MomentObject

<DatePicker value="2018-01-23" onChange={val => console.log(val)} />
// setProps({ value: '2019-01-23' })
// >> "2019-01-23"

<DatePicker value={moment(1581938105000)} onChange={val => console.log(val)} />
// setProps({ value: moment(1581938105000) })
// >> "2020-02-17"
```

## API

### DatePicker

| 参数                 | 说明                                                                     | 类型                                                               | 默认值   | 是否必填 |
| -------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------ | -------- | -------- |
| label                | 输入框内置标签                                                           | React.ReactNode                                                    | -        |          |
| state                | 输入框状态                                                               | 'success' \| 'loading' \| 'error'                                  | -        |          |
| placeholder          | 输入提示                                                                 | string                                                             | -        |          |
| defaultVisibleMonth  | 默认展现的月                                                             | () => Moment                                                       | -        |          |
| defaultVisibleYear   | 默认展现的年                                                             | () => Moment                                                       | -        |          |
| value                | 日期值（受控）moment 对象                                                | string \| Moment \| null                                           | -        |          |
| defaultValue         | 初始日期值，moment 对象                                                  | string \| Moment \| null                                           | -        |          |
| format               | 日期值的格式（用于限定用户输入和展示）                                   | string                                                             | 'YYYY-MM |          |
| showTime             | 是否使用时间控件，传入 TimePicker 的属性 \{ defaultValue, format, ... \} | TimePickerProps \| boolean                                         | false    |          |
| resetTime            | 每次选择日期时是否重置时间（仅在 showTime 开启时有效）                   | boolean                                                            | false    |          |
| disabledDate         | 禁用日期函数                                                             | (date: Moment, view: string) => boolean                            | -        |          |
| footerRender         | 自定义面板页脚                                                           | () => React.ReactNode                                              | -        |          |
| onChange             | 日期值改变时的回调                                                       | (value: string \| Moment \| null) => void                          | -        |          |
| onOk                 | 点击确认按钮时的回调                                                     | (value: string \| Moment \| null) => void                          | -        |          |
| size                 | 输入框尺寸                                                               | 'small' \| 'medium' \| 'large'                                     | 'medium' |          |
| disabled             | 是否禁用                                                                 | boolean                                                            | -        |          |
| hasClear             | 是否显示清空按钮                                                         | boolean                                                            | true     |          |
| visible              | 弹层显示状态                                                             | boolean                                                            | -        |          |
| defaultVisible       | 弹层默认是否显示                                                         | boolean                                                            | false    |          |
| onVisibleChange      | 弹层展示状态变化时的回调                                                 | (visible: boolean, reason: string) => void                         | -        |          |
| onVisibleMonthChange | 弹层展示月份变化时的回调                                                 | (value: Moment, reason: string) => void                            | -        |          |
| popupTriggerType     | 弹层触发方式                                                             | 'click' \| 'hover'                                                 | 'click'  |          |
| popupAlign           | 弹层对齐方式，具体含义见 OverLay 文档                                    | string                                                             | 'tl tl'  |          |
| popupContainer       | 弹层容器                                                                 | PopupProps['container']                                            | -        |          |
| popupStyle           | 弹层自定义样式                                                           | React.CSSProperties                                                | -        |          |
| popupClassName       | 弹层自定义样式类                                                         | string                                                             | -        |          |
| popupProps           | 弹层其他属性                                                             | React.PropsWithRef\<PopupProps>                                    | -        |          |
| inputProps           | 输入框其他属性                                                           | InputProps                                                         | -        |          |
| dateCellRender       | 自定义日期渲染函数                                                       | (calendarDate: Moment) => React.ReactNode                          | -        |          |
| monthCellRender      | 自定义月份渲染函数                                                       | (calendarDate: Moment) => React.ReactNode                          | -        |          |
| yearCellRender       | 自定义年份渲染函数                                                       | (calendarDate: Moment) => React.ReactNode                          | -        |          |
| dateInputAriaLabel   | 日期输入框的 aria-label 属性                                             | string                                                             | -        |          |
| timeInputAriaLabel   | 时间输入框的 aria-label 属性                                             | string                                                             | -        |          |
| isPreview            | 是否为预览态                                                             | boolean                                                            | -        |          |
| renderPreview        | 预览态定制渲染函数                                                       | (value: Moment \| null, props: DatePickerProps) => React.ReactNode | -        |          |
| followTrigger        | 是否跟随滚动                                                             | boolean                                                            | -        |          |
| popupComponent       | 自定义弹层                                                               | React.ComponentType\<unknown>                                      | -        |          |
| popupContent         | 自定义弹层内容                                                           | React.ReactElement                                                 | -        |          |
| disableChangeMode    | 禁用日期选择器的日期模式切换                                             | boolean                                                            | -        |          |
| yearRange            | 年份范围，[START_YEAR, END_YEAR]                                         | [start: number, end: number]                                       | -        |          |

### DatePicker.MonthPicker

| 参数               | 说明                                   | 类型                                                     | 默认值   | 是否必填 |
| ------------------ | -------------------------------------- | -------------------------------------------------------- | -------- | -------- |
| label              | 输入框内置标签                         | React.ReactNode                                          | -        |          |
| state              | 输入框状态                             | 'success' \| 'loading' \| 'error'                        | -        |          |
| placeholder        | 输入提示                               | string                                                   | -        |          |
| defaultVisibleYear | 默认展现的年                           | () => Moment \| null                                     | -        |          |
| value              | 日期值（受控）moment 对象              | string \| Moment \| null                                 | -        |          |
| defaultValue       | 初始日期值，moment 对象                | string \| Moment \| null                                 | -        |          |
| format             | 日期值的格式（用于限定用户输入和展示） | string                                                   | 'YYYY    |          |
| disabledDate       | 禁用日期函数                           | (date: Moment, view: string) => boolean                  | -        |          |
| footerRender       | 自定义面板页脚                         | () => React.ReactNode                                    | -        |          |
| onChange           | 日期值改变时的回调                     | (value: Moment \| string \| null) => void                | -        |          |
| size               | 输入框尺寸                             | 'small' \| 'medium' \| 'large'                           | 'medium' |          |
| disabled           | 是否禁用                               | boolean                                                  | -        |          |
| hasClear           | 是否显示清空按钮                       | boolean                                                  | true     |          |
| visible            | 弹层显示状态                           | boolean                                                  | -        |          |
| defaultVisible     | 弹层默认是否显示                       | boolean                                                  | -        |          |
| onVisibleChange    | 弹层展示状态变化时的回调               | (visible: boolean, reason: string) => void               | -        |          |
| popupTriggerType   | 弹层触发方式                           | 'click' \| 'hover'                                       | 'click'  |          |
| popupAlign         | 弹层对齐方式，具体含义见 OverLay 文档  | string                                                   | 'tl tl'  |          |
| popupContainer     | 弹层容器                               | PopupProps['container']                                  | -        |          |
| popupStyle         | 弹层自定义样式                         | React.CSSProperties                                      | -        |          |
| popupClassName     | 弹层自定义样式类                       | string                                                   | -        |          |
| popupProps         | 弹层其他属性                           | React.PropsWithRef\<PopupProps>                          | -        |          |
| popupComponent     | 自定义弹层                             | React.ComponentType\<unknown>                            | -        |          |
| popupContent       | 自定义弹层内容                         | React.ReactElement                                       | -        |          |
| followTrigger      | 是否跟随滚动                           | boolean                                                  | -        |          |
| inputProps         | 输入框其他属性                         | InputProps                                               | -        |          |
| monthCellRender    | 自定义月份渲染函数                     | (calendarDate: Moment) => React.ReactNode                | -        |          |
| dateInputAriaLabel | 日期输入框的 aria-label 属性           | string                                                   | -        |          |
| renderPreview      | 预览态定制渲染函数                     | (value: Moment \| null, props: MonthPickerProps) => void | -        |          |
| yearCellRender     | 自定义年份渲染函数                     | (calendarDate: Moment) => React.ReactNode                | -        |          |
| isPreview          | 是否为预览态                           | boolean                                                  | -        |          |

### DatePicker.RangePicker

| 参数                    | 说明                                                                     | 类型                                                                                                                                                              | 默认值   | 是否必填 |
| ----------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------- |
| type                    | 日期范围类型                                                             | 'date' \| 'month' \| 'year'                                                                                                                                       | -        |          |
| defaultVisibleMonth     | 默认展示的起始月份                                                       | () => Moment \| null                                                                                                                                              | -        |          |
| placeholder             | 输入提示                                                                 | Array\<string> \| string                                                                                                                                          | -        |          |
| value                   | 日期范围值数组 [moment, moment]                                          | [start: Moment \| string \| null \| undefined, end?: Moment \| string \| undefined \| null]                                                                       | -        |          |
| defaultValue            | 初始的日期范围值数组 [moment, moment]                                    | [<br/> start: Moment \| string \| null \| undefined,<br/> end?: Moment \| string \| undefined \| null,<br/> ]                                                     | -        |          |
| format                  | 日期值的格式（用于限定用户输入和展示）                                   | string                                                                                                                                                            | -        |          |
| showTime                | 是否使用时间控件，传入 TimePicker 的属性 \{ defaultValue, format, ... \} | \| (Omit\<TimePickerProps, 'defaultValue'> & {<br/> defaultValue?: Moment \| string \| null \| (Moment \| string \| null \| undefined)[];<br/> })<br/> \| boolean | false    |          |
| resetTime               | 每次选择日期时是否重置时间（仅在 showTime 开启时有效）                   | boolean                                                                                                                                                           | false    |          |
| disabledDate            | 禁用日期函数                                                             | (date: Moment, view: string) => boolean                                                                                                                           | -        |          |
| footerRender            | 自定义面板页脚                                                           | () => React.ReactNode                                                                                                                                             | -        |          |
| onChange                | 日期范围值改变时的回调                                                   | (value: (string \| Moment \| null \| undefined)[]) => void                                                                                                        | -        |          |
| onOk                    | 点击确认按钮时的回调 返回开始时间和结束时间                              | (value: (string \| Moment \| null \| undefined)[]) => void                                                                                                        | -        |          |
| label                   | 输入框内置标签                                                           | React.ReactNode                                                                                                                                                   | -        |          |
| state                   | 输入框状态                                                               | 'error' \| 'loading' \| 'success'                                                                                                                                 | -        |          |
| size                    | 输入框尺寸                                                               | 'small' \| 'medium' \| 'large'                                                                                                                                    | 'medium' |          |
| disabled                | 是否禁用                                                                 | boolean                                                                                                                                                           | -        |          |
| hasClear                | 是否显示清空按钮                                                         | boolean                                                                                                                                                           | true     |          |
| visible                 | 弹层显示状态                                                             | boolean                                                                                                                                                           | -        |          |
| defaultVisible          | 弹层默认是否显示                                                         | boolean                                                                                                                                                           | false    |          |
| onVisibleChange         | 弹层展示状态变化时的回调                                                 | (visible: boolean, reason: string) => void                                                                                                                        | -        |          |
| popupTriggerType        | 弹层触发方式                                                             | 'click' \| 'hover'                                                                                                                                                | 'click'  |          |
| popupAlign              | 弹层对齐方式，具体含义见 OverLay 文档                                    | string                                                                                                                                                            | 'tl tl'  |          |
| popupContainer          | 弹层容器                                                                 | PopupProps['container']                                                                                                                                           | -        |          |
| popupStyle              | 弹层自定义样式                                                           | React.CSSProperties                                                                                                                                               | -        |          |
| popupClassName          | 弹层自定义样式类                                                         | string                                                                                                                                                            | -        |          |
| popupProps              | 弹层其他属性                                                             | React.PropsWithRef\<PopupProps>                                                                                                                                   | -        |          |
| inputProps              | 输入框其他属性                                                           | InputProps                                                                                                                                                        | -        |          |
| dateCellRender          | 自定义日期渲染函数                                                       | () => void                                                                                                                                                        | -        |          |
| startDateInputAriaLabel | 开始日期输入框的 aria-label 属性                                         | string                                                                                                                                                            | -        |          |
| startTimeInputAriaLabel | 开始时间输入框的 aria-label 属性                                         | string                                                                                                                                                            | -        |          |
| endDateInputAriaLabel   | 结束日期输入框的 aria-label 属性                                         | string                                                                                                                                                            | -        |          |
| endTimeInputAriaLabel   | 结束时间输入框的 aria-label 属性                                         | string                                                                                                                                                            | -        |          |
| renderPreview           | 预览态定制渲染函数                                                       | (<br/> value: [Moment \| null, Moment \| null],<br/> props: RangePickerProps<br/> ) => React.ReactNode                                                            | -        |          |
| onVisibleMonthChange    | 展现的月份变化时的回调                                                   | RangeCalendarProps['onVisibleMonthChange']                                                                                                                        | -        |          |
| popupComponent          | 自定义弹层                                                               | React.ComponentType\<unknown>                                                                                                                                     | -        |          |
| popupContent            | 自定义弹层内容                                                           | React.ReactElement                                                                                                                                                | -        |          |
| monthCellRender         | 自定义月份渲染函数                                                       | (calendarDate: Moment) => React.ReactNode                                                                                                                         | -        |          |
| yearCellRender          | 自定义年份渲染函数                                                       | (calendarDate: Moment) => React.ReactNode                                                                                                                         | -        |          |
| followTrigger           | 是否跟随滚动                                                             | boolean                                                                                                                                                           | -        |          |
| isPreview               | 是否为预览态                                                             | boolean                                                                                                                                                           | -        |          |
| yearRange               | 年份范围，[START_YEAR, END_YEAR]                                         | [start: number, end: number]                                                                                                                                      | -        |          |
| disableChangeMode       | 禁用日期选择器的日期模式切换                                             | boolean                                                                                                                                                           | false    |          |

### DatePicker.YearPicker

| 参数               | 说明                                   | 类型                                                               | 默认值   | 是否必填 |
| ------------------ | -------------------------------------- | ------------------------------------------------------------------ | -------- | -------- |
| label              | 输入框内置标签                         | React.ReactNode                                                    | -        |          |
| state              | 输入框状态                             | 'success' \| 'loading' \| 'error'                                  | -        |          |
| placeholder        | 输入提示                               | string                                                             | -        |          |
| value              | 日期值（受控）moment 对象              | string \| Moment \| null                                           | -        |          |
| defaultValue       | 初始日期值，moment 对象                | string \| Moment \| null                                           | -        |          |
| format             | 日期值的格式（用于限定用户输入和展示） | string                                                             | 'YYYY'   |          |
| disabledDate       | 禁用日期函数                           | (date: Moment, view: string) => boolean                            | -        |          |
| footerRender       | 自定义面板页脚                         | () => React.ReactNode                                              | -        |          |
| onChange           | 日期值改变时的回调                     | (value: Moment \| string \| null) => void                          | -        |          |
| size               | 输入框尺寸                             | 'small' \| 'medium' \| 'large'                                     | 'medium' |          |
| disabled           | 是否禁用                               | boolean                                                            | -        |          |
| hasClear           | 是否显示清空按钮                       | boolean                                                            | true     |          |
| visible            | 弹层显示状态                           | boolean                                                            | -        |          |
| defaultVisible     | 弹层默认是否显示                       | boolean                                                            | -        |          |
| onVisibleChange    | 弹层展示状态变化时的回调               | (visible: boolean, reason: string) => void                         | -        |          |
| popupTriggerType   | 弹层触发方式                           | 'click' \| 'hover'                                                 | 'click'  |          |
| popupAlign         | 弹层对齐方式，具体含义见 OverLay 文档  | string                                                             | 'tl tl'  |          |
| popupContainer     | 弹层容器                               | PopupProps['container']                                            | -        |          |
| popupStyle         | 弹层自定义样式                         | React.CSSProperties                                                | -        |          |
| popupClassName     | 弹层自定义样式类                       | string                                                             | -        |          |
| popupProps         | 弹层其他属性                           | React.PropsWithRef\<PopupProps>                                    | -        |          |
| inputProps         | 输入框其他属性                         | InputProps                                                         | -        |          |
| dateInputAriaLabel | 日期输入框的 aria-label 属性           | string                                                             | -        |          |
| renderPreview      | 预览态定制渲染函数                     | (value: Moment \| null, props: DatePickerProps) => React.ReactNode | -        |          |
| popupComponent     | 自定义弹层                             | React.ComponentType\<unknown>                                      | -        |          |
| popupContent       | 自定义弹层内容                         | React.ReactElement                                                 | -        |          |
| followTrigger      | 是否跟随滚动                           | boolean                                                            | -        |          |
| yearCellRender     | 自定义年份渲染函数                     | (calendarDate: Moment) => React.ReactNode                          | -        |          |
| isPreview          | 是否为预览态                           | boolean                                                            | -        |          |

### DatePicker.WeekPicker

| 参数                 | 说明                                   | 类型                                                               | 默认值   | 是否必填 |
| -------------------- | -------------------------------------- | ------------------------------------------------------------------ | -------- | -------- |
| value                | 日期值（受控）moment 对象              | string \| Moment \| null                                           | -        |          |
| defaultValue         | 初始日期值，moment 对象                | string \| Moment \| null                                           | -        |          |
| visible              | 弹层显示状态                           | boolean                                                            | -        |          |
| defaultVisible       | 弹层默认是否显示                       | boolean                                                            | -        |          |
| format               | 日期值的格式（用于限定用户输入和展示） | string                                                             | 'GGGG    |          |
| onChange             | 日期值改变时的回调                     | (value: Moment \| string \| null) => void                          | -        |          |
| onVisibleChange      | 弹层展示状态变化时的回调               | (visible: boolean, reason: string) => void                         | -        |          |
| renderPreview        | 预览态定制渲染函数                     | (value: Moment \| null, props: DatePickerProps) => React.ReactNode | -        |          |
| dateCellRender       | 自定义日期渲染函数                     | (calendarDate: Moment) => React.ReactNode                          | -        |          |
| label                | 输入框内置标签                         | React.ReactNode                                                    | -        |          |
| state                | 输入框状态                             | 'success' \| 'loading' \| 'error'                                  | -        |          |
| defaultVisibleMonth  | 默认展现的月                           | () => Moment                                                       | false    |          |
| onVisibleMonthChange | 弹层展示月份变化时的回调               | (value: Moment, reason: string) => void                            | -        |          |
| disabledDate         | 禁用日期函数                           | (date: Moment, view: string) => boolean                            | -        |          |
| footerRender         | 自定义面板页脚                         | () => React.ReactNode                                              | -        |          |
| size                 | 输入框尺寸                             | 'small' \| 'medium' \| 'large'                                     | 'medium' |          |
| disabled             | 是否禁用                               | boolean                                                            | -        |          |
| hasClear             | 是否显示清空按钮                       | boolean                                                            | true     |          |
| popupTriggerType     | 弹层触发方式                           | 'click' \| 'hover'                                                 | 'click'  |          |
| popupAlign           | 弹层对齐方式，具体含义见 OverLay 文档  | string                                                             | 'tl tl'  |          |
| popupContainer       | 弹层容器                               | PopupProps['container']                                            | -        |          |
| popupStyle           | 弹层自定义样式                         | React.CSSProperties                                                | -        |          |
| popupClassName       | 弹层自定义样式类                       | string                                                             | -        |          |
| popupProps           | 弹层其他属性                           | React.PropsWithRef\<PopupProps>                                    | -        |          |
| popupComponent       | 自定义弹层                             | React.ComponentType\<unknown>                                      | -        |          |
| popupContent         | 自定义弹层内容                         | React.ReactElement                                                 | -        |          |
| followTrigger        | 是否跟随滚动                           | boolean                                                            | -        |          |
| inputProps           | 输入框其他属性                         | InputProps                                                         | -        |          |
| monthCellRender      | 自定义月份渲染函数                     | (calendarDate: Moment) => React.ReactNode                          | -        |          |
| yearCellRender       | 自定义年份渲染函数                     | (calendarDate: Moment) => React.ReactNode                          | -        |          |
| isPreview            | 是否为预览态                           | boolean                                                            | -        |          |

## 无障碍键盘操作指南

同选择框一样聚焦到 DatePiker 后，需要按下 `ENTER` 键打开弹出框，选择/输入日期，通过 `TAB` 切换日期和时间输入框。

| 按键            | 说明                                                            |
| :-------------- | :-------------------------------------------------------------- |
| 数字键          | 需要手动输入日期，指定的日期格式                                |
| Enter           | 打开日期选择框或输入后选择日期                                  |
| Esc             | 关闭日期选择框                                                  |
| Up              | 输入上一天（Month Picker 则是上一个月，Year Picker 则是上一年） |
| Down            | 输入下一天（Month Picker 则是下一个月，Year Picker 则是下一年） |
| Page Up         | 输入上一月                                                      |
| Page Down       | 输入下一月                                                      |
| Alt + Page Up   | 输入上一年                                                      |
| Alt + Page Down | 输入下一年                                                      |


---


## date-picker2

# zh-CN order=0

# 基本用法

最基本的用法。可以通过 `onChange` 监听选中值的变化。

# en-US order=0

# Basic

A basic usage case.


---


## date-picker2

# zh-CN order=8

# 面板的默认展现日期

可以通过 `defaultPanelValue`属性可以修改面板的默认展现日期。

# en-US order=8

# Default visible date

Change default visible date by setting `defaultPanelValue`.


---


## date-picker2

# zh-CN order=2

# 禁用

选择框的不可用状态。你也可以通过数组单独禁用 `RangePicker` 的其中一项。

# en-US order=2

# Disable dates

A disabled state of the `DatePicker`. You can also set as array to disable one of input.


---


## date-picker2

# zh-CN order=3

# 禁止选择某些日期

可以通过 `disabledDate` 属性来禁止用户选择或输入某些特定日期。

# en-US order=3

# Disable dates

Disable date cells by `disabledDate`.


---


## date-picker2

# zh-CN order=11

# 自定义面板页脚

可以通过 `extraFooterRender` 自定义对面板页脚的定制。

# en-US order=11

# Footer

Passing custom footer with `extraFooterRender`.


---


## date-picker2

# zh-CN order=5

# 格式化

使用`format`属性，可以自定义日期显示格式。

# en-US order=5

# Basic

Using attribute `format` to change the displayed dates, it will be also used to check user inputs.


---


## date-picker2

# zh-CN order=9

# 无边框

无边框样式。

# en-US order=9

# Borderless

borderless style.


---


## date-picker2

# zh-CN order=7

# 预设时间快捷选择

通过`preset`预设时间快捷选择。

# en-US order=7

# Basic

A preset usage case.


---


## date-picker2

# zh-CN order=1

# 范围选择

指定范围选择器类型。

# en-US order=1

# RangePicker

Choose a RangePicker.


---


## date-picker2

# zh-CN order=4

# 选择不超过七天的范围

使用 onCalendarChange 和 disabledDate 来限制动态的日期区间选择。

# en-US order=4

# Select range dates in 7 days

Using onCalendarChange and disabledDate to limit date selection.


---


## date-picker2

# zh-CN order=6

# 日期时间选择

如果需要同时选择时间，可以通过 `showTime` 属性开启，`timePanelProps` 支持传入`TimePickerPanel`的属性，例如 `format`, `defaultValue` 等。

# en-US order=6

# With time

Enable `showTime` to create a DatePicker2/RangePicker with time.


---


## date-picker2

# zh-CN order=10

# 尺寸大小

通过 `size` 属性设置输入框大小，默认`medium`。

# en-US order=10

# Format

Using attribute `size` to change the input size, `medium` as default.


---


## date-picker2

# DatePicker2

-   category: Components
-   family: DataEntry
-   chinese: 日期选择框
-   type: 表单
-   version: 1.22.0

---

输入或选择日期的控件。当用户需要输入一个日期，可以点击标准输入框，弹出日期面板进行选择。

## 开发指南
### 从 `DatePicker` 升级到 `DatePicker2`
1.22版本增加当前组件

功能变化：
- 交互重构，面板和输入框分离，优化底部扩展等
- 使用 `dayjs` 日期库替换了 `moment`
- 新增`WeekPicker` 和 `QuarterPicker` 选择器
- 新增了 `preset` 属性，支持预设日期

API变化：
- 移除了 `defaultVisibleMonth` 属性，请使用 `defaultPanelValue` 替代（仅名字替换）
- 移除了 `footerRender` 属性，请使用 `extraFooterRender` 替代
- `showTime` 之前属性类型既支持 `Boolean` 也支持 `Object`；现升级为仅支持 `Boolean` 类型，使用 `timePanelProps` 来传入时分秒的时间选择属性
- `onChange` 和 `onOk` 等事件返回日期对象为 `Dayjs` 类型

### 国际化
日期的国际化包括组件的国际化跟[日期库`dayjs`的国际化](https://dayjs.gitee.io/docs/zh-CN/i18n/i18n)两部分。
```jsx
import { DatePicker2, ConfigProvider } from '@alifd/next';
import 'dayjs/locale/en'; // 组件库国际化
import en from '@alifd/next/lib/locale/en-us'; // 组件国际化

function App() {
    return (
        <ConfigProvider locale={en}>
          <DatePicker2 />
        </ConfigProvider>
    );
}
ReactDOM.render(<App />, mountNode);
```

## API
日期选择框分为 `DatePicker` 和 `RangePicker` 两种类型，分别又有 `date`、`month`、`year`, `week`, `quarter` 五种不同模式。
### 公共API

| 参数                  | 说明                                                                                                                                                                                                                                                                   | 类型             | 默认值          |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- | ------------ |
| disabledDate        | 禁用日期函数<br><br>**签名**:<br>Function(value: Dayjs, view: String) => Boolean<br>**参数**:<br>_value_: {Dayjs} 日期值<br>_mode_: {String} 当前视图类型<br>**返回值**:<br>{Boolean} 是否禁用<br>                                                       | Function       | () => false  |
| dateCellRender      | 自定义日期渲染函数<br><br>**签名**:<br>Function(value: Object) => ReactNode<br>**参数**:<br>_value_: {Dayjs} 日期值<br>**返回值**:<br>{ReactNode} node节点<br>                                                                                                                   | Function       | -            |
| onPanelChange       | 日历面板切换的回调<br><br>**签名**:<br>Function(value: Dayjs, mode: String) => void<br>**参数**:<br>_value_: {Dayjs} 日期对象                                                                                                                                                                                                                                              | Function        | -            |
| showTime            | 是否使用时间控件                                                                                                                                                                                                          | Boolean | false        |
| resetTime           | 每次选择日期时是否重置时间                                                                                                                                                                                                                                    | Boolean        | false        |
| preset              | 预设日期快捷选择                                                                                                      | Object       | -            |
| extraFooterRender   | 自定义额外的页脚<br><br>**签名**:<br>Function() => ReactNode<br>**返回值**:<br>{ReactNode} 自定义的面板页脚组件<br>                                                                                                                                                                                    | Function       | () => null   |
| disabled            | 是否禁用                                                                                                                                                                                                                                                                 | Boolean        | false            |
| hasClear            | 是否显示清空按钮                                                                                                                                                                                                                                                             | Boolean        | true         |
| size                | 输入框尺寸<br><br>**可选值**:<br>`small`, `medium`, `large`                                                                                                                                                                                                                  | Enum           | `medium`     |
| inputReadOnly       | 只读                                                                                                                                                                                                                           | Boolean        | false     |
| inputProps          | 输入框其他属性                                                                                                                                                                                                                                                              | Object         | -            |
| visible             | 弹层显示状态                                                                                                                                                                                                                                                               | Boolean        | -            |
| defaultVisible      | 弹层默认是否显示                                                                                                                                                                                                                                                             | Boolean        | false        |
| onVisibleChange     | 弹层展示状态变化时的回调<br><br>**签名**:<br>Function(visible: Boolean) => void<br>**参数**:<br>_visible_: {Boolean} 弹层是否显示 | Function       | func.noop    |
| popupTriggerType    | 弹层触发方式<br><br>**可选值**:<br>'click', 'hover'                                                                                                                                                                                                                           | Enum           | 'click'      |
| popupAlign          | 弹层对齐方式,具体含义见 OverLay文档                                                                                                                                                                                                                                               | String         | 'tl tl'      |
| popupContainer      | 弹层容器                                                                                                                                                                                                                                                                 | any            | -            |
| popupStyle          | 弹层自定义样式                                                                                                                                                                                                                                                              | Object         | -            |
| popupClassName      | 弹层自定义样式类                                                                                                                                                                                                                                                             | String         | -            |
| popupProps          | 弹层其他属性                                                                                                                                                                                                                                                               | Object         | -            |
| followTrigger       | 是否跟随滚动                                                                                                                                                                                                                                                               | Boolean        | -            |
| popupProps          | 弹层其他属性                                                                                                                                                                                                                                                               | Object         | -            |
| isPreview           | 是否为预览态                                                                                                                                                                                                                                                               | Boolean        | -            |
| renderPreview       | 预览态模式下渲染的内容<br><br>**签名**:<br>Function(value: Dayjs) => void<br>**参数**:<br>_value_: {Dayjs} 日期                                                                                                                                                         | Function       | -            |
| dateInputAriaLabel  | 日期输入框的 aria-label 属性                                                                                                                                                                                                                                                 | String         | -            |

### DatePicker2 (YearPicker/MonthPicker/WeekPicker/QuarterPicker)

| 参数                 | 说明                                                                                                                                                                                                                                             | 类型        | 默认值         |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | ----------- |
| placeholder        | 输入提示                                                                                                                                                                                                                                           | String    | -           |
| value              | 日期值（受控）                                                                                                                                                                                                                               | Dayjs/String    | -           |
| defaultValue       | 初始日期值                                                                                                                                                                                                                                | Dayjs/String    | -           |
| format             | 日期格式                                                                                                                                                                                                                            | String    | `YYYY-MM`   |
| outputFormat       | 输出格式                                                                                                                                                                                                                            | String | ((date: Dayjs, dateStr: String) => any)   |   |
| onChange           | 日期值改变时的回调<br><br>**签名**:<br>Function(value: Dayjs/String) => void<br>**参数**:<br>_value_: {Dayjs/String} 日期值                                                                                                                      | Function  | func.noop   |
| onOk               | 点击确认按钮时的回调<br><br>**签名**:<br>Function() => Array<br>**返回值**:<br>{Array} 日期范围<br>                                                                                              | Function             | func.noop

### DatePicker2.RangePicker

| 参数                      | 说明                                                                                                                                                                                                                                      | 类型                   | 默认值
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | -------------------------------------------------------------------------------------------- |
| mode               | 日期面板的状态<br><br>**可选值**:<br>`date`、`month`、`year`, `week`, `quarter`                                                                                                                                                                    | Enum           | `date`     |
| placeholder        | 输入提示                                                                                                                                                                                                                                           | String | [String, String]    | -           |
| value              | 日期值（受控）                                                                                                                                                                                                               | [Dayjs, Dayjs]                | -    |
| defaultValue       | 初始日期值                                                                                                                                                                                                         | [Dayjs, Dayjs]                 | -    |
| format             | 日期格式                                                                                                                                                                                                                                    | String/Function               | `YYYY-MM`         |
| outputFormat       | 输出格式                                                                                                                                                                                                                            | String | ((date: [Dayjs, Dayjs], dateStr: [String, String]) => any)   |   |
| onChange           | 日期值改变时的回调<br><br>**签名**:<br>Function(value) => void<br>**参数**:<br>_value_: {[Dayjs, Dayjs]} 日期范围                                                                                                                      | Function  | func.noop   |
| onCalendarChange           | 待选日期发生变化的回调<br><br>**签名**:<br>Function(value, dateStrings) => void<br>**参数**:<br>_value_: {[Dayjs, Dayjs]} 日期范围<br>dateStrings: {[string, string]}                                                                                                                     | Function  | func.noop   |
| onOk               | 点击确认按钮时的回调<br><br>**签名**:<br>Function(value) => void<br>**参数**:<br>_value_: {[Dayjs, Dayjs]} 日期范围<br>                                                                                              | Function             | func.noop


---


## dialog

# zh-CN order=9

# 无障碍支持

通过`okProps`与`cancelProps`设置`aria-label`属性，屏幕阅读器读取确定和取消按钮。关于键盘操作请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=9

# Accessibility

Set the `aria-label` attribute via `okProps` and `cancelProps`, The screen reader will read the OK and Cancel buttons. Please refer to `ARIA and KeyBoard` for keyboard operation.


---


## dialog

# zh-CN order=0

# 基本

基本用法，打开和关闭。

# en-US order=0

# Basic

First dialog


---


## dialog

# zh-CN order=2

# 自定义底部

默认的底部为确定取消两个按钮，可以通过 `okProps` 或 `cancelProps` 自定义按钮属性，或者通过 `footer` 属性完全自定义底部内容。

# en-US order=2

# Customize footer

The default `footer` is ok and cancel buttons, you can customize `footer` content.


---


## dialog

# zh-CN order=12

# 可拖拽

可拖拽弹窗。

# en-US order=0

# Basic

dragable dialog


---


## dialog

# zh-CN order=3

# 定制底部按钮

通过 `footerActions` 来调整确定按钮和取消按钮是否出现以及相互间的位置，通过 `footerAlign` 来调整底部按钮的对齐方式。

# en-US order=3

# Customize buttons of footer

Use footerActions to control the position of the OK and Cancel buttons and their mutual position. Use footerAlign to control the alignment of the bottom buttons.


---


## dialog

# zh-CN order=5

# 固定高度

使用 `height` 属性设置 `Dialog` 整体高度。

# en-US order=8

# Set fixed Dialog height

Use `height` prop to set Dialog height style. Will also position footer at bottom.


---


## dialog

# zh-CN order=4

# 滚动条

当对话框内容超出视窗时候，对话框默认撑开高度，会出现滚动条。可以通过设置 `overflowScroll` 让对话框出现滚动条。

# en-US order=4

# Large content dialog

When the height of the dialog exceeds the viewport height of the browser, the default is to have the scroll bar appear in the body area of the dialog. This ensures that the bottom button can appear directly in the viewport, which is convenient to operate. If you don't want to show a scroll bar, please set overflowScroll to true to show all the content of the dialog.


---


## dialog

# zh-CN order=2

# 确认对话框/延迟关闭

在使用 `Dialog.alert`，`Dialog.confirm` 以及 `Dialog.show` 时，如果 `onOk` 返回 `Promise`，对话框会在 `Promise` resolve 时关闭，除非调用 `resolve(false)`。

# en-US order=6

# Delay close

When using `Dialog.alert`, `Dialog.confirm`, and `Dialog.show`, if `onOk` returns a `Promise`, the dialog will close when the `Promise` resolves, unless `resolve(false)` is called.


---


## dialog

# zh-CN order=1

# 快捷调用

`Dialog` 提供 `alert` 和 `confirm` 的快掉调用方式，以及更底层的 `show` 方式。

# en-US order=1

# Quick call

The `Dialog` provides quick methods called `alert` and `confirm`, as well as a lower-level `show` method.


---


## dialog

# zh-CN order=7

# 国际化 withContext

通过 `Dialog.withContext(({ contextDialog }) => {} )`方法，封装 使用到函数式调用弹窗 的组件（例如业务组件或者当前App等），可以将 被封装组件 代码所在上下文的`context`注入到`context` `Dialog`中。

相比较`Dialog.alert()`获取到的是当前页面第一次被记录且未被卸载`的context`，`contextDialog.alert()`获取到的是 下例中`< DialogWitchContext />` 所在代码环境的`context`。

`contextDialog`上可被调用的方法有`alert` `confirm` `show`，注意`contextDialog`只有`Dialog`的函数式调用方法，它不能像 `<Dialog />` 一样被使用。

# en-US order=7

# withContext

Use `Dialog.withContext` to render Dialog imperatively. It is recommended over `Dialog.alert/confirm/show` because it get fusion config(.e.g prefix, locale) from context.


---


## dialog

# Dialog

-   chinese: 弹窗
-   family: Feedback
-   category: Components
-   type: 弹层

---

对话框。

## 何时使用

对话框是用于在不离开主路径的情况下，提供用户快速执行简单的操作、确认用户信息或反馈提示的辅助窗口。

### `v2` 版本更新指示

1.25 版本增加 v2 api 支持开启新版本弹窗，功能如下

功能变化：

-   位置不再通过 js 计算，通过 css 完成，响应式性能更好
-   新增 `closeIcon` 可定制关闭按钮 icon
-   新增 `width` 固定弹窗宽度，默认值为 520px, 或者设置 auto 跟随内容变化。
-   新增 `dialogRender` 配合 `react-draggable` 以支持拖拽弹窗

API 变化：

-   移除了 `align` `shouldUpdatePosition`, Dialog 会自动调整位置
-   移除了 `minMargin` , 改用 `top` `bottom`
-   移除了 `isFullScreen` ，改用 `overflowScroll` 默认开启超出滚动

## API

### Dialog

| 参数                 | 说明                                                                                                                                                                             | 类型                                                                               | 默认值                                 | 是否必填 | 支持版本 |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------- | -------- | -------- |
| visible              | 是否显示                                                                                                                                                                         | boolean                                                                            | false                                  |          | -        |
| title                | 标题                                                                                                                                                                             | React.ReactNode                                                                    | -                                      |          | -        |
| children             | 内容                                                                                                                                                                             | React.ReactNode                                                                    | -                                      |          | -        |
| footer               | 底部内容，设置为 false，则不进行显示                                                                                                                                             | boolean \| React.ReactNode                                                         | -                                      |          | -        |
| footerAlign          | 底部按钮的对齐方式                                                                                                                                                               | 'left' \| 'center' \| 'right'                                                      | 'right'                                |          | -        |
| footerActions        | 指定确定按钮和取消按钮是否存在以及如何排列                                                                                                                                       | Array\<'ok' \| 'cancel'>                                                           | ['ok', 'cancel']                       |          | -        |
| cache                | 隐藏时是否保留子节点，不销毁                                                                                                                                                     | boolean                                                                            | false                                  |          | 1.23     |
| onOk                 | 在点击确定按钮时触发的回调函数                                                                                                                                                   | (event: React.MouseEvent) => void                                                  | -                                      |          | -        |
| onCancel             | 在点击取消按钮时触发的回调函数                                                                                                                                                   | (event: React.MouseEvent) => void                                                  | -                                      |          | -        |
| okProps              | 应用于确定按钮的属性对象                                                                                                                                                         | ButtonProps                                                                        | -                                      |          | -        |
| cancelProps          | 应用于取消按钮的属性对象                                                                                                                                                         | ButtonProps                                                                        | -                                      |          | -        |
| closeable            | [废弃] 同 closeMode, 控制对话框关闭的方式                                                                                                                                        | 'close' \| 'mask' \| 'esc' \| boolean \| 'close,mask' \| 'close,esc' \| 'mask,esc' | 'esc,close'                            |          | -        |
| closeMode            | [推荐] 控制对话框关闭的方式                                                                                                                                                      | CloseMode[] \| CloseMode                                                           | -                                      |          | 1.21     |
| onClose              | 对话框关闭时触发的回调函数                                                                                                                                                       | (trigger: string, event: React.MouseEvent \| KeyboardEvent) => void                | -                                      |          | -        |
| afterClose           | 对话框关闭后触发的回调函数，如果有动画，则在动画结束后触发                                                                                                                       | () => void                                                                         | -                                      |          | -        |
| hasMask              | 是否显示遮罩                                                                                                                                                                     | boolean                                                                            | true                                   |          | -        |
| animation            | 显示隐藏时动画的播放方式                                                                                                                                                         | Record\<'in' \| 'out', string> \| false                                            | \{ in: 'fadeInUp', out: 'fadeOutUp' \} |          | -        |
| autoFocus            | 对话框弹出时是否自动获得焦点                                                                                                                                                     | boolean                                                                            | false                                  |          | -        |
| align                | [v2 废弃] 对话框对齐方式，具体见 Overlay 文档                                                                                                                                    | string \| boolean                                                                  | -                                      |          | -        |
| isFullScreen         | [v2 废弃] 当对话框高度超过浏览器视口高度时，是否显示所有内容而不是出现滚动条以保证对话框完整显示在浏览器视口内，该属性仅在对话框垂直水平居中时生效，即 align 被设置为 'cc cc' 时 | boolean                                                                            | -                                      |          | -        |
| shouldUpdatePosition | [v2 废弃] 是否在对话框重新渲染时及时更新对话框位置，一般用于对话框高度变化后依然能保证原来的对齐方式                                                                             | boolean                                                                            | -                                      |          | -        |
| minMargin            | [v2 废弃] 对话框距离浏览器顶部和底部的最小间距，align 被设置为 'cc cc' 并且 isFullScreen 被设置为 true 时不生效                                                                  | number                                                                             | 40                                     |          | -        |
| overlayProps         | 透传到弹层组件的属性对象                                                                                                                                                         | OverlayProps                                                                       | -                                      |          | -        |
| locale               | 自定义国际化文案对象                                                                                                                                                             | Partial\<{<br/> ok: string;<br/> cancel: string;<br/> }>                           | -                                      |          | -        |
| height               | 对话框的高度样式属性                                                                                                                                                             | string \| number                                                                   | -                                      |          | -        |
| width                | 弹窗宽度                                                                                                                                                                         | string \| number                                                                   | -                                      |          | 1.25     |
| popupContainer       | 自定义弹窗挂载位置                                                                                                                                                               | string \| HTMLElement \| ((target?: HTMLElement) => HTMLElement)                   | -                                      |          | -        |
| v2                   | 开启 v2 版本弹窗                                                                                                                                                                 | false \| undefined                                                                 | false                                  |          | -        |
| noPadding            | 去除 body 内间距                                                                                                                                                                 | boolean                                                                            | false                                  |          | 1.26     |
| closeIcon            | 定制关闭按钮 icon                                                                                                                                                                | React.ReactNode                                                                    | -                                      |          | 1.25     |

### Dialog V2

| 参数             | 说明                                                                                                                                                                             | 类型                                                                | 默认值                                 | 是否必填 | 支持版本 |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- | -------------------------------------- | -------- | -------- |
| visible          | 是否显示                                                                                                                                                                         | boolean                                                             | false                                  |          | -        |
| title            | 标题                                                                                                                                                                             | React.ReactNode                                                     | -                                      |          | -        |
| children         | 内容                                                                                                                                                                             | React.ReactNode                                                     | -                                      |          | -        |
| footer           | 底部内容，设置为 false，则不进行显示                                                                                                                                             | boolean \| React.ReactNode                                          | -                                      |          | -        |
| footerAlign      | 底部按钮的对齐方式                                                                                                                                                               | 'left' \| 'center' \| 'right'                                       | 'right'                                |          | -        |
| footerActions    | 指定确定按钮和取消按钮是否存在以及如何排列                                                                                                                                       | Array\<'ok' \| 'cancel'>                                            | ['ok', 'cancel']                       |          | -        |
| cache            | 隐藏时是否保留子节点，不销毁                                                                                                                                                     | boolean                                                             | false                                  |          | 1.23     |
| onOk             | 在点击确定按钮时触发的回调函数                                                                                                                                                   | (event: React.MouseEvent) => void                                   | -                                      |          | -        |
| onCancel         | 在点击取消按钮时触发的回调函数                                                                                                                                                   | (event: React.MouseEvent) => void                                   | -                                      |          | -        |
| okProps          | 应用于确定按钮的属性对象                                                                                                                                                         | ButtonProps                                                         | -                                      |          | -        |
| cancelProps      | 应用于取消按钮的属性对象                                                                                                                                                         | ButtonProps                                                         | -                                      |          | -        |
| closeMode        | [推荐] 控制对话框关闭的方式                                                                                                                                                      | CloseMode[] \| CloseMode                                            | -                                      |          | 1.21     |
| onClose          | 对话框关闭时触发的回调函数                                                                                                                                                       | (trigger: string, event: React.MouseEvent \| KeyboardEvent) => void | -                                      |          | -        |
| afterClose       | 对话框关闭后触发的回调函数，如果有动画，则在动画结束后触发                                                                                                                       | () => void                                                          | -                                      |          | -        |
| hasMask          | 是否显示遮罩                                                                                                                                                                     | boolean                                                             | true                                   |          | -        |
| animation        | 显示隐藏时动画的播放方式                                                                                                                                                         | Record\<'in' \| 'out', string> \| false                             | \{ in: 'fadeInUp', out: 'fadeOutUp' \} |          | -        |
| autoFocus        | 对话框弹出时是否自动获得焦点                                                                                                                                                     | boolean                                                             | false                                  |          | -        |
| isFullScreen     | [v2 废弃] 当对话框高度超过浏览器视口高度时，是否显示所有内容而不是出现滚动条以保证对话框完整显示在浏览器视口内，该属性仅在对话框垂直水平居中时生效，即 align 被设置为 'cc cc' 时 | boolean                                                             | -                                      |          | -        |
| minMargin        | [v2 废弃] 对话框距离浏览器顶部和底部的最小间距，align 被设置为 'cc cc' 并且 isFullScreen 被设置为 true 时不生效                                                                  | number                                                              | 40                                     |          | -        |
| overlayProps     | 透传到弹层组件的属性对象                                                                                                                                                         | OverlayProps                                                        | -                                      |          | -        |
| locale           | 自定义国际化文案对象                                                                                                                                                             | Partial\<{<br/> ok: string;<br/> cancel: string;<br/> }>            | -                                      |          | -        |
| height           | 对话框的高度样式属性                                                                                                                                                             | string \| number                                                    | -                                      |          | -        |
| popupContainer   | 自定义弹窗挂载位置                                                                                                                                                               | string \| HTMLElement \| ((target?: HTMLElement) => HTMLElement)    | -                                      |          | -        |
| v2               | 开启 v2 版本弹窗                                                                                                                                                                 | true                                                                | false                                  |          | -        |
| closeIcon        | 定制关闭按钮 icon                                                                                                                                                                | React.ReactNode                                                     | -                                      |          | 1.25     |
| width            | 弹窗宽度                                                                                                                                                                         | string \| number                                                    | -                                      |          | 1.25     |
| noPadding        | 去除 body 内间距                                                                                                                                                                 | boolean                                                             | false                                  |          | 1.26     |
| top              | [v2] 弹窗上边距。默认 100，设置 centered=true 后默认 40                                                                                                                          | number                                                              | -                                      |          | 1.25     |
| bottom           | [v2] 弹窗下边距                                                                                                                                                                  | number                                                              | 40                                     |          | 1.25     |
| overflowScroll   | [v2] 对话框高度超过浏览器视口高度时，对话框是否展示滚动条。关闭此功后对话框会随高度撑开页面                                                                                      | boolean                                                             | -                                      |          | 1.25     |
| centered         | [v2] 弹窗居中对齐                                                                                                                                                                | boolean                                                             | -                                      |          | 1.25     |
| dialogRender     | [v2] 自定义渲染弹窗                                                                                                                                                              | (modal: React.ReactNode) => React.ReactNode                         | -                                      |          | -        |
| wrapperClassName | [v2] 最外包裹层 className                                                                                                                                                        | string                                                              | -                                      |          | 1.26     |
| wrapperStyle     | [v2] 最外包裹层 style                                                                                                                                                            | React.CSSProperties                                                 | -                                      |          | 1.26     |

<!-- api-extra-start -->

### Dialog.alert(config)/Dialog.confirm(config)

以下只列举 config 可以传入的常用属性，Dialog 组件的其他属性也可以传入

| 属性         | 说明                           | 类型      | 默认值   |
| :----------- | :----------------------------- | :-------- | :------- |
| title        | 标题                           | ReactNode | ''       |
| content      | 内容                           | ReactNode | ''       |
| onOk         | 在点击确定按钮时触发的回调函数 | Function  | () => {} |
| onCancel     | 在点击取消按钮时触发的回调函数 | Function  | () => {} |
| messageProps | 内嵌 Message 组件属性对象      | Object    | {}       |

### Dialog.show

以下只列举 config 可以传入的常用属性，Dialog 组件其他属性也可以传入

| 属性     | 说明                           | 类型      | 默认值   |
| :------- | :----------------------------- | :-------- | :------- |
| title    | 标题                           | ReactNode | ''       |
| content  | 内容                           | ReactNode | ''       |
| onOk     | 在点击确定按钮时触发的回调函数 | Function  | () => {} |
| onCancel | 在点击取消按钮时触发的回调函数 | Function  | () => {} |

### Dialog.withContext

上面的`Dialog.alert/confirm/show`这种命令式 API，虽然使用起来很方便，但是如果你的应用使用了多次`ConfigProvider`，当你通过命令式 API 调起的 Dialog 的时候，它到底会使用哪份 fusion config（比如 prefix、文案），是一件无法确定的事情（详见[#2005](https://github.com/alibaba-fusion/next/issues/2005)）。你可以从 withContext Example 看到这个问题。

为了解决这个问题，我们提供了一个新的 API：`Dialog.withContext`。
对于要使用命令式 API 的组件，使用`Dialog.withContext`HOC 来包裹一下。然后你就可以在你的组件 props.contextDialog 拿到 `alert, confirm, show` 这 3 个命令式方法。通过这 3 个方法来调起的 Dialog，它使用的 fusion config 是符合预期的。请看 withContext Example 的使用示例。

<!-- api-extra-end -->

## 无障碍键盘操作指南

| 键盘      | 说明                                                                       |
| :-------- | :------------------------------------------------------------------------- |
| esc       | 按下 ESC 键将会关闭 dialog 而不触发任何的动作                              |
| tab       | 正向聚焦到任何可以被聚焦的元素，在 Dialog 显示的时候，焦点始终保持在框体内 |
| shift+tab | 反向聚焦到任何可以被聚焦的元素，在 Dialog 显示的时候，焦点始终保持在框体内 |

## FAQ

### 对话框高度发生变化时无法感知重新使用 JS 定位？

Dialog 组件默认使用 JS 进行定位，当内容过长时使用 JS 自动调整对话框高度，以使得操作按钮在可视区域内出现，但是这会造成在对话框高度发生变化时无法感知重新使用 JS 定位，有下面两种解决方案：

1.  设置 `shouldUpdatePosition`，在内容更新后，会重新进行定位。

2.  使用 `isFullScreen`，启动 CSS 进行定位，无论对话框高度如何变化都能自适应居中，但是当内容过长时无法让操作按钮在可视区域内出现。


---


## divider

# zh-CN order=3

# 无障碍支持

分割线默认不会被聚焦。

# en-US order=3

# Basic Usage

Divider will not be focused under any circumstance.


---


## divider

# zh-CN order=0

# 基本

简单的分隔符展示。

# en-US order=0

# Basic Usage

Simple usage of Divider component.


---


## divider

# zh-CN order=1

# 垂直展示

通过`direction`设置垂直分隔符展示。

# en-US order=1

# Direction

Set vertical Divider using `direction`.


---


## divider

# zh-CN order=2

# 带文案的分割线

通过 `orientation` 来设置分割线上文案的位置。

# en-US order=2

# Basic Usage

Divider with different orientation of text.


---


## divider

# Divider

-   category: Components
-   family: General
-   chinese: 分隔符
-   type: 展示
-   version: 1.19

---

区隔内容的分割线, 支持版本 1.19 及以上。

## 何时使用

-   对不同章节的文本段落进行分割。
-   对行内文字/链接进行分割，例如表格的操作列。

## API

### Divider

| 参数        | 说明                 | 类型                          | 默认值   | 是否必填 |
| ----------- | -------------------- | ----------------------------- | -------- | -------- |
| dashed      | 是否为虚线           | boolean                       | false    |          |
| direction   | 线是水平还是垂直类型 | 'hoz' \| 'ver'                | 'hoz'    |          |
| orientation | 分割线标题的位置     | 'left' \| 'right' \| 'center' | 'center' |          |

## 无障碍键盘操作指南

分割线默认不会聚焦，无键盘操作。


---


## drawer

# zh-CN order=0

# 基本

第一个抽屉

# en-US order=0

# Basic

First drawer


---


## drawer

# zh-CN order=2

# 双层抽屉

双层抽屉，抽屉内打开新的抽屉

# en-US order=2

# Basic

Double drawer


---


## drawer

# zh-CN order=1

# 自定义弹出方向

自定义弹出方向

# en-US order=1

# Basic

Diffrent placement


---


## drawer

# zh-CN order=6

# 快捷调用

快捷调用

# en-US order=0

# Quick

First drawer


---


## drawer

# zh-CN order=3

# 抽屉式选择

将 Select 的弹出模式换成 Drawer

# en-US order=3

# Drawer Select

Select width drawer


---


## drawer

# zh-CN order=5

# 宽高

可以通过 width 设置容器宽度，或者设置 width=auto 自适应内容宽度

# en-US order=0

# Size

First drawer


---


## drawer

# Drawer

-   chinese: 抽屉
-   family: Feedback
-   category: Components
-   type: 弹层

---

抽屉组件。

## 何时使用

抽屉是用于在不离开主路径的情况下，提供用户快速执行简单的操作、确认用户信息或反馈提示的辅助窗口。

### `v2` 版本更新指示

1.25 版本增加 v2 api 支持开启新版本弹窗，功能如下

功能变化：

-   位置不再通过 js 计算，通过 css 完成，响应式性能更好
-   支持设置 `width/height` 固定弹窗宽度, 或者设置 auto 跟随内容变化
-   支持 Drawer.show() 快捷调用

## API

### Drawer

| 参数            | 说明                                                                                                  | 类型                                                                               | 默认值                                       | 是否必填 | 支持版本 |
| --------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------- | -------- | -------- |
| closeable       | [废弃] 同 closeMode, 控制对话框关闭的方式，                                                           | 'close' \| 'mask' \| 'esc' \| boolean \| 'close,mask' \| 'close,esc' \| 'mask,esc' | true                                         |          | -        |
| closeMode       | [推荐] 控制对话框关闭的方式                                                                           | CloseMode \| CloseMode[]                                                           | -                                            |          | 1.21     |
| cache           | 隐藏时是否保留子节点，不销毁                                                                          | boolean                                                                            | -                                            |          | -        |
| title           | 标题                                                                                                  | React.ReactNode                                                                    | -                                            |          | -        |
| bodyStyle       | body 上的样式                                                                                         | React.CSSProperties                                                                | -                                            |          | -        |
| headerStyle     | header 上的样式                                                                                       | React.CSSProperties                                                                | -                                            |          | -        |
| animation       | 显示隐藏时动画的播放方式<br/><br/>**签名**:<br/>**参数**:<br/>_animation_: 指定进场和出场动画的对象。 | { in: string; out: string } \| false                                               | \{ in: 'expandInDown', out: 'expandOutUp' \} |          | -        |
| visible         | 是否显示                                                                                              | boolean                                                                            | -                                            |          | -        |
| width           | 宽度，仅在 placement 是 left right 的时候生效                                                         | number \| string                                                                   | -                                            |          | -        |
| height          | 高度，仅在 placement 是 top bottom 的时候生效                                                         | number \| string                                                                   | -                                            |          | -        |
| onClose         | 对话框关闭时触发的回调函数                                                                            | (reason: string, e: React.MouseEvent \| KeyboardEvent) => void                     | `() => {}`                                   |          | -        |
| placement       | 位于页面的位置                                                                                        | 'top' \| 'right' \| 'bottom' \| 'left'                                             | 'right'                                      |          | -        |
| v2              | 开启 v2                                                                                               | false \| undefined                                                                 | false                                        |          | -        |
| content         | 内容                                                                                                  | React.ReactNode                                                                    | -                                            |          | -        |
| popupContainer  | 渲染组件的容器                                                                                        | string \| HTMLElement \| null                                                      | -                                            |          | -        |
| hasMask         | 是否显示遮罩                                                                                          | boolean                                                                            | true                                         |          | -        |
| afterOpen       | [v2 废弃] 对话框打开后的回调函数                                                                      | () => void                                                                         | -                                            |          | -        |
| onVisibleChange | [v2 废弃] 受控模式下 (没有 trigger 的时候)，只会在关闭时触发，相当于 onClose                          | (visible: boolean, reason: string, e?: React.MouseEvent) => void                   | -                                            |          | -        |

### Drawer V2

| 参数           | 说明                                                                                                  | 类型                                                                               | 默认值                                       | 是否必填 | 支持版本 |
| -------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------- | -------- | -------- |
| closeable      | [废弃] 同 closeMode, 控制对话框关闭的方式，                                                           | 'close' \| 'mask' \| 'esc' \| boolean \| 'close,mask' \| 'close,esc' \| 'mask,esc' | true                                         |          | -        |
| closeMode      | [推荐] 控制对话框关闭的方式                                                                           | CloseMode \| CloseMode[]                                                           | -                                            |          | 1.21     |
| cache          | 隐藏时是否保留子节点，不销毁                                                                          | boolean                                                                            | -                                            |          | -        |
| title          | 标题                                                                                                  | React.ReactNode                                                                    | -                                            |          | -        |
| bodyStyle      | body 上的样式                                                                                         | React.CSSProperties                                                                | -                                            |          | -        |
| headerStyle    | header 上的样式                                                                                       | React.CSSProperties                                                                | -                                            |          | -        |
| animation      | 显示隐藏时动画的播放方式<br/><br/>**签名**:<br/>**参数**:<br/>_animation_: 指定进场和出场动画的对象。 | { in: string; out: string } \| false                                               | \{ in: 'expandInDown', out: 'expandOutUp' \} |          | -        |
| visible        | 是否显示                                                                                              | boolean                                                                            | -                                            |          | -        |
| width          | 宽度，仅在 placement 是 left right 的时候生效                                                         | number \| string                                                                   | -                                            |          | -        |
| height         | 高度，仅在 placement 是 top bottom 的时候生效                                                         | number \| string                                                                   | -                                            |          | -        |
| afterClose     | [v2] 弹窗关闭后的回调                                                                                 | () => void                                                                         | -                                            |          | -        |
| onClose        | 对话框关闭时触发的回调函数                                                                            | (reason: string, e: React.MouseEvent \| KeyboardEvent) => void                     | `() => {}`                                   |          | -        |
| placement      | 位于页面的位置                                                                                        | 'top' \| 'right' \| 'bottom' \| 'left'                                             | 'right'                                      |          | -        |
| v2             | 开启 v2                                                                                               | true                                                                               | false                                        |          | -        |
| content        | 内容                                                                                                  | React.ReactNode                                                                    | -                                            |          | -        |
| popupContainer | 渲染组件的容器                                                                                        | string \| HTMLElement \| null                                                      | -                                            |          | -        |
| hasMask        | 是否显示遮罩                                                                                          | boolean                                                                            | true                                         |          | -        |

### CloseMode

```typescript
export type CloseMode = 'close' | 'mask' | 'esc';
```

<!-- api-extra-start -->

### Drawer.show

以下只列举 config 可以传入的常用属性，Drawer 组件其他属性也可以传入

| 属性    | 说明 | 类型      | 默认值 |
| :------ | :--- | :-------- | :----- |
| title   | 标题 | ReactNode | ''     |
| content | 内容 | ReactNode | ''     |

### Drawer.withContext

上面的`Drawer.show`这种命令式API，虽然使用起来很方便，但是如果你的应用使用了多次`ConfigProvider`，当你通过命令式API调起的Drawer的时候，它到底会使用哪份fusion config（比如prefix、文案），是一件无法确定的事情（详见[#2005](https://github.com/alibaba-fusion/next/issues/2005)）。你可以从 withContext Example 看到这个问题。

为了解决这个问题，我们提供了一个新的API：`Drawer.withContext`。
对于要使用命令式API的组件，使用`Drawer.withContext`HOC来包裹一下。然后你就可以在你的组件props.contextDrawer拿到 `show` 命令式方法。

<!-- api-extra-end -->

## 无障碍键盘操作指南

| 键盘      | 说明                                                                      |
| :-------- | :------------------------------------------------------------------------ |
| esc       | 按下ESC键将会关闭dialog而不触发任何的动作                                 |
| tab       | 正向聚焦到任何可以被聚焦的元素， 在Dialog显示的时候，焦点始终保持在框体内 |
| shift+tab | 反向聚焦到任何可以被聚焦的元素，在Dialog显示的时候，焦点始终保持在框体内  |


---


## dropdown

# zh-CN order=3

# 无障碍支持

若要使用无障碍的 Dropdown，推荐使用`<Dropdown triggerType={["click", "hover"]}>` (请勿使用 triggerType="focus")。菜单类元素需要由用户确认后再展开才是一种无障碍友好的实践。

# en-US order=3

# Accessibility

Use `<Dropdown triggerType={["click", "hover"]}>` to make Dropdown better accessibility.


---


## dropdown

# zh-CN order=0

# 基本

最简单的用法。

# en-US order=0

# Basic

Basic usage.


---


## dropdown

# zh-CN order=2

# 从弹层外关闭

使用 visible 属性控制弹层显示或者隐藏，需要使用 safeNode 将其控制的元素告诉 dropdown 组件。

# en-US order=2

# Close the Overlay from Outside

You can set `visible` attribute to control overlay display or hidden, and you should tell dropdown component what it controls by `safeNode` attribute.


---


## dropdown

# zh-CN order=1

# 触发的事件类型

使用 triggerType 设置触发的事件类型。

# en-US order=1

# Close the Overlay from Outside

You can set event type which trigger overlay by `triggerType` attribute.


---


## dropdown

# Dropdown

-   category: Components
-   family: Util
-   chinese: 下拉菜单
-   type: 弹层

---

下拉弹窗组件。

## 何时使用

当页面上的操作命令过多时，用此组件可以收纳操作元素。点击或移入触点，会出现一个下拉菜单。可在列表中进行选择，并执行相应的命令。

## API

### Dropdown

继承 Popup 绝大多数属性，除了 canCloseByOutSideClick, autoFocus，以下列举为常用属性，其他可参考 Overlay 文档

| 参数            | 说明                                                                                                           | 类型                                              | 默认值                                       | 是否必填 |
| --------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- | -------------------------------------------- | -------- |
| autoClose       | 开启后，children 不管是不是 Menu，点击后都默认关掉弹层（2.x 默认设置为 true）                                  | boolean                                           | false                                        |          |
| children        | 弹层内容                                                                                                       | React.ReactElement                                | -                                            | 是       |
| visible         | 弹层当前是否显示                                                                                               | boolean                                           | -                                            |          |
| align           | 弹层相对于触发元素的定位，详见 Overlay 的定位部分                                                              | string                                            | 'tl bl'                                      |          |
| offset          | 弹层相对于触发元素定位的微调                                                                                   | Array\<number>                                    | [0, 0]                                       |          |
| hasMask         | 是否显示遮罩                                                                                                   | boolean                                           | false                                        |          |
| animation       | 配置动画的播放方式，支持 \{in: 'enter-class', out: 'leave-class' \} 的对象参数，如果设置为 false，则不播放动画 | string \| false \| Record\<'in' \| 'out', string> | \{ in: 'expandInDown', out: 'expandOutUp' \} |          |
| trigger         | 触发弹层显示或者隐藏的元素                                                                                     | React.ReactElement                                | -                                            | 是       |
| triggerType     | 触发弹层显示或隐藏的操作类型，可以是 'click'，'hover'，或者它们组成的数组，如 ['hover', 'click']               | PopupProps['triggerType']                         | 'hover'                                      |          |
| defaultVisible  | 弹层默认是否显示                                                                                               | boolean                                           | false                                        |          |
| onVisibleChange | 弹层显示或隐藏时触发的回调函数                                                                                 | PopupProps['onVisibleChange']                     | -                                            |          |
| disabled        | 设置此属性，弹层无法显示或隐藏                                                                                 | PopupProps['disabled']                            | false                                        |          |
| delay           | 弹层显示或隐藏的延时时间（以毫秒为单位），在 triggerType 被设置为 hover 时生效                                 | PopupProps['delay']                               | 200                                          |          |

## 无障碍键盘操作指南

| 按键        | 说明                                                                           |
| :---------- | :----------------------------------------------------------------------------- |
| Up Arrow    | 垂直模式下，同级导航，导航到前一项                                             |
| Down Arrow  | 垂直模式下，同级导航，导航到后一项                                             |
| Right Arrow | 垂直模式下，打开子菜单，导航到子菜单第一项；水平模式下，同级导航，导航到后一项 |
| Left Arrow  | 垂直模式下，关闭子菜单，导航到父级菜单；水平模式下，同级导航，导航到前一项     |
| Enter       | 打开子菜单，导航到子菜单第一项                                                 |
| Esc         | 关闭子菜单，导航到父级菜单                                                     |


---


## field

# zh-CN order=6

# 自动卸载

autoUnmount 默认为 true，当组件被 unmount 的时候会自动删除数据. autoUnmount 设置为 false 后，会一直保存数据.

# en-US order=6

# basic

autoUnmount is true by default, and data will be deleted automatically. Field will keep data while autoUnmount is set to false.


---


## field

# zh-CN order=0

# 基本

`getValue` `setValue` `reset` 的使用

# en-US order=0

# basic

usage of `getValue` `setValue` `reset`


---


## field

# zh-CN order=10

# 自定义组件

自己的组件如何接入Field。

`最低标准`: 组件支持 `onChange` 读取组件数据。`达到效果`：Field 可以 getValue，但是 setValue 无效

`完全支持`: 组件支持[受控](https://facebook.github.io/react/docs/forms.html#controlled-components)， 也就是支持两个api：`value` `onChange`. value: 设置组件的数据; onChange: 在组件修改的时候在第一个数暴露数据

# en-US order=10

# custom

`must`: has api of `onChange`, so you can use `getValue` but you can't `setValue`
`perfect support`: has api of `value` `onChange`. value: set data for component; onChange: return first param for component


---


## field

# zh-CN order=6

# 动态表格

通过 `deleteArrayValue/addArrayValue` 可以往数组格式的数据里面 删除/添加 数据, 并且自动订正其他 name 的 偏移问题

# en-US order=6

# mix usage

by use `deleteArrayValue/addArrayValue` could delete and add array , and fix keys offset problem


---


## field

# zh-CN order=12

# Hooks

在 functional component 里可使用 `Field.useField` 支持 hooks. `依赖: react@^16.8`

# en-US order=12

# Hooks

`Field` exposes a React Hook `useField` as a static method. Takes in the `options` parameter used with `new Field(...)`. `dependencies: react@^16.8`


---


## field

# zh-CN order=8

# 组合使用

多组件混合使用

# en-US order=8

# mix usage

multi type of component


---


## field

# zh-CN order=2

# 自定义返回值

当组件返回的数据和最终期望提交的格式不一致的时候，可以使用 `getValueFormatter` 和 `setValueFormatter` 两个函数做转换。

比如 switch 组件期望上报 0/1, date-picker 组件期望上报 YYYY-MM-DD 这种字符串格式

# en-US order=2

# custom event value

eg: you want get 0/1 from switch, or YYYY-MM-DD string from date-picker, you can use `getValueFormatter` 和 `setValueFormatter`


---


## field

# zh-CN order=1

# 关联控制

组件之间的关联控制. `onChange` 统一管理。

# en-US order=1

# controlled

manage value by `onChange`


---


## field

# zh-CN order=5

# redux 中使用

在 redux 中使用, 在 `componentWillReceiveProps` 更新

# en-US order=5

# with redux

set value in `componentWillReceiveProps`


---


## field

# zh-CN order=3

# 自定义错误

自己控制组件的errors

# en-US order=3

# custom errors

set errors of component by yourself


---


## field

# zh-CN order=11

# 结构化解析

通过配置 `parseName=true`，可以实现如下效果：

把 `init('obj.b')` 的数据转换成 `obj={obj:{b:'value'}}`；

把 `init('arr.0')` 的数据转换成 `obj={arr:['']}`；

# en-US order=11

# Parse Array or Object

By pass `parseName=true` you can achieve the following effects:

from `init('obj.b')` to `obj={obj:{b:'value'}}`；

from `init('arr.0')` to `obj={arr:['']}`；


---


## field

# zh-CN order=4

# 校验

校验的错误信息需要用`getError`获取

`注意`：Form 和 Field 做了深度结合，在 Form 中使用Field，错误信息不需`getError`获取会自动展现。

请参考 validatorPromise demo，以使用 Promise 而不是回调

# en-US order=4

# validate

you can easily use validate in `Form`, or you can use `getError` to set errors where you want to put. See `validatorPromise` demo to use promises instead of callbacks.


---


## field

# zh-CN order=4

# 校验 promise

使用 Promise 的方式作为校验返回

# en-US order=4

# validate Promise

validate form values with errors returned wrapped in a promise. Also supports callbacks. If the callback returns a promise, the results of the promise will be returned in a promise from the `validate` function.


---


## field

# zh-CN order=9

# 自定义受控字段

valueName 的默认值为 value，如果为其他需要用 valueName 指定

# en-US order=9

# custom valueName

default valueName is `value`


---


## field

# zh-CN order=13

# Watch

使用 `field.watch` 或 `Field.useWatch` 来监听字段值变化. `Field.useWatch` 是一个react hook, 依赖 `react@^16.8`.

# en-US order=13

# Watch

Use `field.watch` or `Field.useWatch` to watch the value change event of field. `Field.useWatch` is a react hook, depend `react@^16.8`.


---


## field

# Field

-   category: Components
-   family: DataEntry
-   chinese: 表单辅助工具
-   cols: 1
-   type: 表单

---

表单数据管理组件。

## 何时使用

涉及到表单数据操作、校验的地方都可以用Field来管理数据。和组件关联后可以自动对表单数据进行回写、读取、校验。

## 如何使用

-   使用Field `init` 过的组件, `value` `onChange` 必须放在 init 的第三个参数, 否则有可能被 init 覆盖。
-   `Form`已经和`Field` 在`数据获取`和`自动校验提示`方面做了深度优化，建议在`Form`中使用`Field`, 请查看 Form demo。
-   initValue 类似组件的 defaultValue 只有在组件第一次render的时候才生效(ajax 异步调用设置 initValue 可能已经错过了第一次render)
-   autoUnmount 默认打开的，如果需要保留会 `自动卸载的组件` 数据请关闭此项
-   `parseName=true` 可以通过 `getValues` 获取到结构化的数据, 但是 getValue 还是必须传完整 key 值
-   `PureComponent` 中无法使用，除非你开启 `forceUpdate` 功能，但是会带来性能问题

### 基本使用

```jsx
class Demo extends React.Component {
    field = new Field(this); // 实例创建

    onClick = () => {
        console.log(this.field.getValue('name'));
    };
    render() {
        const init = this.field.init;

        // 注意：initValue只会在组件第一次初始化的时候被赋值，如果你是异步赋值请用setValue
        return (
            <div>
                <Input {...init('name', { initValue: 'first value' })} />
                <button onClick={this.onClick}>获取数据</button>
            </div>
        );
    }
}
```

### 更新数据

#### 事件更新

```jsx
class Demo extends React.Component {
    field = new Field(this);

    onClick = () => {
        this.field.setValue('name', 'newvalue'); // 赋值会自动触发render
    };
    render() {
        const init = this.field.init;

        return (
            <div>
                <Input {...init('name')} />
                <button onClick={this.onClick}>设置数据</button>
            </div>
        );
    }
}
```

#### props更新

```jsx
class Demo extends React.Component {
    field = new Field(this);

    // 在组件挂载之前把数据设置进去(可以用initValue替代这种用法)
    componentWillMount() {
        this.field.setValue('name', 'init Name');
    }
    // 接收来自props的数据
    componentWillReceiveProps(nextProps) {
        this.field.setValue('name', nextProps.name);
    }
    render() {
        const init = this.field.init;

        return (
            <div>
                <Input {...init('name')} />
            </div>
        );
    }
}
```

#### ajax更新

```jsx
class Demo extends React.Component {
    field = new Field(this);

    onClick = () => {
        Ajax({
            url: '/demo.json',
            success: json => {
                // 回调事件中赋值更新
                this.field.setValue('name', json.name);
            },
        });
    };
    render() {
        const init = this.field.init;

        return (
            <div>
                <Input {...init('name')} />
                <button onClick={this.onClick}>设置数据</button>
            </div>
        );
    }
}
```

#### onChange更新监控

两种用法：

1. 统一管理

```jsx
class Demo extends React.Component {
    field = new Field(this, {
        onChange: (name, value) => {
            switch (name) {
                case 'name1':
                    this.field.setValue('name2', 'value set by name1');
                    break;
                case 'name2':
                    this.field.setValue('name1', 'value set by name2');
                    break;
            }
        },
    });
    render() {
        const init = this.field.init;

        return (
            <div>
                <Input {...init('name1')} />
                <Input {...init('name2')} />
            </div>
        );
    }
}
```

2. 各自管理

```jsx
class Demo extends React.Component {
    render() {
        const init = this.field.init;

        return (
            <div>
                <Input
                    {...init('name1', {
                        props: {
                            onChange: v => {
                                this.field.setValue('name2', 'value set by name1');
                            },
                        },
                    })}
                />
                <Input
                    {...init('name2', {
                        props: {
                            onChange: v => {
                                this.field.setValue('name1', 'value set by name2');
                            },
                        },
                    })}
                />
            </div>
        );
    }
}
```

详细请查看demo演示 [#关联控制](#onchange-container)。

## API

<!-- api-extra-start -->

```jsx
let myfield = new Field(this [,options]);

// 或者使用hooks

let myfield = Field.useField([options]); // 要求 react 版本 > 16.8
```

### Field参数说明

| 参数    | 说明                       | 类型            | 可选值   | 默认值 |
| ------- | -------------------------- | --------------- | -------- | ------ |
| this    | 传入调用class的this        | React.Component | 必须设置 |        |
| options | 一些事件配置, 详细参数如下 | Object          | 非必须   |        |

### `options` 配置项

| 参数               | 说明                                                                                                                           | 类型                 | 默认值 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------ | -------------------- | ------ |
| onChange           | 所有组件的change都会到达这里[setValue不会触发该函数]                                                                           | Function(name,value) |        |
| parseName          | 是否翻译`init(name)`中的`name`(getValues会把带`.`的字符串转换成对象)                                                           | Boolean              | false  |
| forceUpdate        | 仅建议PureComponent的组件打开此强制刷新功能，会带来性能问题(500个组件为例：打开的时候render花费700ms, 关闭时候render花费400ms) | Boolean              | false  |
| scrollToFirstError | field.validate的时候滚动到第一个出错的组件, 如果是整数会进行偏移, 浏览器兼容性关注`scrollIntoViewIfNeeded`                     | Boolean/Number       | true   |
| autoUnmount        | 自动删除Unmout元素，如果想保留数据可以设置为false                                                                              | Boolean              | true   |
| autoValidate       | 是否修改数据的时候就自动触发校验, 设为 false 后只能通过 validate() 来触发校验                                                  | Boolean              | true   |
| values             | 初始化数据                                                                                                                     | Object               | -      |

### 接口说明

`new`之后的对象提供的api接口 （例：`myfield.getValues()`）(`set` 开头的api函数不要在render里面操作, 可能会触发死循环)

| 参数             | 说明                                                                   | 类型                                                                                                                                                          | 可选值                         | 默认值 |
| ---------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ | ------ |
| init             | 初始化每个组件，[详细参数如#init函数](#init函数)                       | Function(name:String, option:Object)                                                                                                                          |                                |        |
| getValues        | 获取一组输入控件的值，如不传入参数，则获取全部组件的值                 | Function([names: String[]])                                                                                                                                   |                                |        |
| getValue         | 获取单个输入控件的值                                                   | Function(name: String)                                                                                                                                        |                                |        |
| setValues        | 设置一组输入控件的值（会触发render，请遵循react时机使用)               | Function(obj: Object)                                                                                                                                         |                                |        |
| setValue         | 设置单个输入控件的值 （会触发render，请遵循react时机使用)              | Function(name: String, value)                                                                                                                                 |                                |        |
| validate         | 校验并获取一组输入域的值与 Error                                       | Function([names: String[]], callback: Function(errors, values))                                                                                               |                                |        |
| getError         | 获取单个输入控件的 Error                                               | Function(name: String)                                                                                                                                        |                                |        |
| getErrors        | 获取一组输入控件的 Error                                               | Function([name: String])                                                                                                                                      |                                |        |
| setError         | 设置单个输入控件的 Error                                               | Function(name: String, errors:String/Array[String])                                                                                                           |                                |        |
| setErrors        | 设置一组输入控件的 Error                                               | Function(obj: Object)                                                                                                                                         |                                |        |
| reset            | 重置一组输入控件的值、清空校验                                         | Function([names: String[]])                                                                                                                                   |                                |        |
| resetToDefault   | 重置一组输入控件的值为默认值                                           | Function([names: String[]])                                                                                                                                   |                                |        |
| getState         | 判断校验状态                                                           | Function(name: String)                                                                                                                                        | 'error' 'success' 'loading' '' | ''     |
| getNames         | 获取所有组件的key                                                      | Function()                                                                                                                                                    |                                |        |
| remove           | 删除某一个或者一组控件的数据，删除后与之相关的validate/value都会被清空 | Function(name: String/String[])                                                                                                                               |                                |        |
| addArrayValue    | 添加 name 是数组格式的数据, 并且自动处理其他 name 的数组错位问题       | Function(key: String, index: Number, value1, value2, ...)                                                                                                     |                                |        |
| deleteArrayValue | 删除 name 是数组格式的数据, 并且自动处理其他 name 的数组错位问题       | Function(key: String, index: Number, howmany)                                                                                                                 |                                |        |
| watch            | 监听字段值变化                                                         | Function(names: String[], callback: Function(name: String, value: any, oldValue: any, triggerType: 'init' \| 'change' \| 'setValue' \| 'unmount' \| 'reset')) |                                |        |

### init函数

```jsx
init(name, options, props);
```

返回值

```jsx
{
    id, value, onChange;
}
```

| 参数                      | 说明                                                                                      | 类型                                               | 可选值 | 默认值     |
| ------------------------- | ----------------------------------------------------------------------------------------- | -------------------------------------------------- | ------ | ---------- | --- |
| name                      | 必填输入控件唯一标志                                                                      | String                                             |        |            |
| options.valueName         | 组件值的属性名称，如 Checkbox 的是 `checked`，Input是 `value`                             | String                                             |        | 'value'    |
| options.initValue         | 组件初始值(组件第一次render的时候才会读取，后面再修改此值无效),类似defaultValue           | any                                                |        |            |
| options.trigger           | 触发数据变化的事件名称                                                                    | String                                             |        | 'onChange' |
| options.rules             | 校验规则                                                                                  | Array/Object                                       |        |            |     |
| options.getValueFormatter | 自定义从组件获取 `value` ，详细用法查看demo `自定义数据获取`                              | Function(value,...args) 参数顺序和组件是完全一致的 |        |            |     |
| options.setValueFormatter | 自定义转换 `value` 到组件 ，详细用法查看demo `自定义数据获取`                             | Function(value)                                    |        |            |     |
| props                     | 组件自定义的事件可以写在这里                                                              | Object                                             |        |            |     |
| autoValidate              | 是否修改数据的时候自动触发校验单个组件的校验, 设为 false 后只能通过 validate() 来触发校验 | Boolean                                            | true   |

### rules参数

```jsx
{
    rules: [{ required: true }];
}
```

多个rule

```jsx
{
    rules: [
        { required: true, trigger: 'onBlur' },
        { pattern: /abcd/, message: 'abcd不能缺', trigger: 'onChange' },
        {
            validator: (rule, value, callback) => {
                callback('出错了');
            },
        },
    ];
}
```

| 参数      | 说明                                                                                                                                                                                                                                     | 类型                          | 可选值                      | 使用类型                             |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- | --------------------------- | ------------------------------------ |
| required  | 不能为空                                                                                                                                                                                                                                 | Boolean                       | true                        | `undefined/null/“”/[]` 会触发此规则) |
| pattern   | 校验正则表达式                                                                                                                                                                                                                           | 正则                          |                             |                                      |
| minLength | 字符串最小长度 / 数组最小个数                                                                                                                                                                                                            | Number                        |                             | String/Number/Array                  |
| maxLength | 字符串最大长度 / 数组最大个数                                                                                                                                                                                                            | Number                        |                             | String/Number/Array                  |
| length    | 字符串精确长度 / 数组精确个数                                                                                                                                                                                                            | Number                        |                             | String/Number/Array                  |
| min       | 最小值                                                                                                                                                                                                                                   | Number                        |                             | String/Number                        |
| max       | 最大值                                                                                                                                                                                                                                   | Number                        |                             | String/Number                        |
| format    | 对常用 pattern 的总结                                                                                                                                                                                                                    | String                        | url、email、tel、number     | String                               |
| validator | 自定义校验, 校验的结果通过用户传递给 callback 的参数决定(校验成功的时候不要忘记执行 `callback()`,否则会校验不返回): <br/> - callback() 无参数表示校验成功 <br/> - callback('this is a error msg') 有参数表示校验失败，并且参数为错误信息 | Function(rule,value,callback) |                             |                                      |
| trigger   | 触发校验的事件名称                                                                                                                                                                                                                       | String/Array                  | onChange/onBlur/onFocus/... | onChange                             |
| message   | 出错时候信息                                                                                                                                                                                                                             | String                        |                             |                                      |

### Field.useWatch

`field.watch` 的 react hook 实现

```typescript
type WatchTriggerType = 'init' | 'change' | 'setValue' | 'unmount' | 'reset';
interface WatchCallback {
    (name: string, value: unknown, oldValue: unknown, triggerType: WatchTriggerType): void;
}
class Field {
    static useWatch: (field: Field, names: string[], callback: WatchCallback) => void;
}
```

<!-- api-extra-end -->

## FAQ

### 自定义组件接入Field标准？

-   支持受控模式(value+onChange) `必须`
    -   value 控制组件数据展现
    -   onChange 组件发生变化时候的回调函数（第一个参数可以给到value)
-   一次完整操作抛一次onChange事件 `建议`
    比如有Process表示进展中的状态，建议增加API `onProcess`；如果有Start表示启动状态，建议增加API `onStart`
-   `value={undefined}`的时候清空数据, field 的 reset 函数会给所有组件下发 undefined 数据 `建议`

```jsx
componentWillReceiveProps(nextProps) {
    if ('value' in nextProps ) {
        this.setState({
           value: nextProps.value === undefined? []: nextProps.value   //  设置组件的被清空后的数值
        })
    }
}
```

### 为何手动调用`this.field.validate`的时候进不了回调函数？

可能是自定义了validator方法，确保`callback`在任何分支下都能被执行到。


---


## form

# zh-CN order=30

# 无障碍支持

对于必填项，在组件中要设置`aria-required`属性，并通过视觉设计上的高亮提示用户。

# en-US order=30

# Accessibility

For required fields, set the `aria-required` attribute in the component and prompt the user with a visual design highlight.


---


## form

# zh-CN order=0

# 基本

表单布局、编辑、提交、校验的基本使用

# en-US order=0

# Basic Usage

basic usage of form edit/submit/validate


---


## form

# zh-CN order=6

# 自定义布局

标签位置：上、左

配合 `Row` `Col` 控制表单内元素布局 (注意：FormItem非Form直接子元素需要不能直接直接在Form上设置布局)

# en-US order=6

# Custom Layout

Label Position: top / left

With `Row` `Col` control the layout of the elements within the form (Note: FormItem is not Form direct child elements can not directly set the layout on the Form)


---


## form

# zh-CN order=18

# 禁用

一键切换元素为禁用态

# en-US order=17

# Disabled

You can switch to disabled state.


---


## form

# zh-CN order=10

# 复杂功能(Field)

配合 `Field` 可以实现较复杂功能

# en-US order=10

# use Field

Complex functions can be realized with `Field`


---


## form

# zh-CN order=1

# 布局

inline 布局只支持横排

# en-US order=1

# Layout


---


## form

# zh-CN order=11

# 表单组合

展示和表单相关的其他组件。

# en-US order=11

# Combination of Form-Component

Display other components related to the Form.


---


## form

# zh-CN order=17&debug=true

# 移动端

device=phone 下会强制设置 labelAlign=top

# en-US order=17

# Basic Usage

force set labelAlign=top while device=phone


---


## form

# zh-CN order=5

# 嵌套

FormItem 嵌套

# en-US order=5

# Nest

FormItem Nest


---


## form

# zh-CN order=7

# 回车提交

需要Form里面有 htmlType="submit" 的元素

# en-US order=7

# Trigger on Press the Enter key

Requires htmlType="submit" element in Form


---


## form

# zh-CN order=17

# 预览态

可以通过Form切换表单元素的预览态，切换前后布局结构相同

# en-US order=17

# Preview

You can switch to preview state. Preview state and editor state share the same layout.


---


## form

# zh-CN order=3

# 注册

验证码获取

# en-US order=10

# save field

send code


---


## form

# zh-CN order=7

# 响应式

可以通过配置 `labelCol` `wrapperCol` 的 `Grid.Col` 响应式属性实现响应式

# en-US order=7

# Responsive

Response can be configured by `Grid.Col` property of `labelCol` `wrapperCol`.


---


## form

# zh-CN order=6&debug=true

# 自适应布局

可通过设置 `device` `responsive` 实现响应式, 1.19.0+ 添加，仅支持ie10+

# en-US order=6

# Responsive Grid

Response can be configured by `device`. Added in 1.19.0+, support ie10+.


---


## form

# zh-CN order=2

# 尺寸

`size` 会强制设置 `FormItem` 下的所有组件的size

`labelAlign` label方位（如果不设置 labelCol 和 wrapperCol 那么默认是标签在上）

`labelTextAlign` 文字左右对齐方式

# en-US order=2

# Size

`size` will specify the size of all components under `FormItem`;

`labelAlign` Align of label. If labelcol and wrappercol are not set, the value is 'top' by default

`labelTextAlign` Align of text inlabel;


---


## form

# zh-CN order=9

# 校验

基本的表单校验例子。

# en-US order=9

# Validate

Basic usage of validation.


---


## form

# zh-CN order=9

# label作为校验提示

使用 label 作为校验提示

# en-US order=9

# Validate

use label as name for validate message


---


## form

# zh-CN order=8

# 校验提示

为 `<FormItem>` 定义 `state` 属性控制三种校验状态。

如果是 `<Input>` 组件, 可在`<FormItem>`上面添加 `hasFeedback` 控制图标的展示

**注意**: 反馈图标只对 `<Input />` 有效。

# en-US order=8

# Valedation prompt

Define the `state` attribute for `<FormItem>` to control the three valedation states.

If it is an `<Input>` component, you can add `hasFeedback` to control icon on `<FormItem>`

**Note**: The feedback icon is only valid for `<Input />`.


---


## form

# Form

-   category: Components
-   family: DataEntry
-   chinese: 表单
-   cols: 1
-   type: 表单

---

表单组件。

## 何时使用

表单布局、校验、数据提交操作时用到。 组件的设计思想可以看这篇文章 <a href="https://zhuanlan.zhihu.com/p/56280821" target="_blank">https&#x3A;//zhuanlan.zhihu.com/p/56280821</a>

## 如何使用

-   组件不要使用关键字 `nodeName` 作为 name、id
-   Form 默认使用 `size=medium`, 并且会控制 FormItem 内所有组件的size。 如果想修改组件的size `<FormItem size="small" >`
-   在垂直表单中如果文字（一般 `<p>` 标签）或者组件向上偏离，可以通过 `className="next-form-text-align"` 辅助调整
-   必须是被 `<FormItem>`直接包裹的组件才能展示校验错误提示。如果界面不展示错误信息，请检查是否有多个层级。 比如 `<FormItem><div><Input/></div></FormItem>` 是无法展示校验信息的。
-   可以通过 `<Form field={false}>` 来关闭数据获取，变成一个纯布局组件

### 关于校验

-   建议一个FormItem放一个组件, 方便错误提示跟随组件展示
-   组件必须是FormItem的第一层子元素
-   详细校验请查看 `Field` 组件文档的 rules

### 复杂表单场景

如果您的表单场景非常复杂，比如动态渲染，大量字段，复杂数据结构，复杂联动校验，可以考虑使用 [formily](https://github.com/alibaba/formily)，formily已经封装了所有fusion组件，保证您开箱即用

## API

### Form

| 参数                      | 说明                                                                                                                                                                                                | 类型                                                                                                                         | 默认值                                               | 是否必填 | 支持版本 |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- | -------- | -------- |
| inline                    | 内联表单                                                                                                                                                                                            | boolean                                                                                                                      | -                                                    |          | -        |
| size                      | 单个 Item 的 size 自定义，优先级高于 Form 的 size, 并且当组件与 Item 一起使用时，组件自身设置 size 属性无效。                                                                                       | 'large' \| 'medium' \| 'small'                                                                                               | medium                                               |          | -        |
| fullWidth                 | 单个 Item 中表单类组件宽度是否是 100%                                                                                                                                                               | boolean                                                                                                                      | -                                                    |          | -        |
| labelAlign                | 标签的位置，如果不设置 labelCol 和 wrapperCol 那么默认是标签在上                                                                                                                                    | 'top' \| 'left' \| 'inset'                                                                                                   | left                                                 |          | -        |
| labelTextAlign            | 标签的左右对齐方式                                                                                                                                                                                  | 'left' \| 'right'                                                                                                            | -                                                    |          | -        |
| field                     | field 实例，传 false 会禁用 field                                                                                                                                                                   | false \| NextField \| null                                                                                                   | -                                                    |          | -        |
| saveField                 | 保存 Form 自动生成的 field 对象                                                                                                                                                                     | (field?: NextField \| null) => void                                                                                          | func.noop                                            |          | -        |
| labelCol                  | 控制第一级 Item 的 labelCol                                                                                                                                                                         | ColProps                                                                                                                     | -                                                    |          | -        |
| wrapperCol                | 控制第一级 Item 的 wrapperCol                                                                                                                                                                       | ColProps                                                                                                                     | -                                                    |          | -        |
| onSubmit                  | form 内有 `htmlType="submit"` 的元素的时候会触发                                                                                                                                                    | FormEventHandler\<HTMLFormElement>                                                                                           | function preventDefault(e) \{ e.preventDefault(); \} |          | -        |
| children                  | 子元素                                                                                                                                                                                              | ReactNode                                                                                                                    | -                                                    |          | -        |
| value                     | 表单数值                                                                                                                                                                                            | FieldValues                                                                                                                  | -                                                    |          | -        |
| onChange                  | 表单变化回调<br/><br/>**签名**:<br/>**参数**:<br/>_values_: 表单数值<br/>_item_: 表单项，item.name：发生变化的组件的名称，item.value：变化的组件的新数据，item.field：与变化的组件关联的 field 实例 | (<br/> values: FieldValues \| undefined,<br/> item: { name: string; value: string; field: NextField \| null }<br/> ) => void | func.noop                                            |          | -        |
| component                 | 设置标签类型                                                                                                                                                                                        | ElementType                                                                                                                  | 'form'                                               |          | -        |
| fieldOptions              | field 配置项，在 Form 初始化 field 实例时会用到                                                                                                                                                     | FieldOption                                                                                                                  | -                                                    |          | -        |
| device                    | 预设屏幕宽度                                                                                                                                                                                        | 'desktop' \| 'phone' \| 'tablet'                                                                                             | 'desktop'                                            |          | -        |
| responsive                | 是否开启内置的响应式布局（使用 ResponsiveGrid）                                                                                                                                                     | boolean                                                                                                                      | -                                                    |          | 1.19     |
| isPreview                 | 是否开启预览态                                                                                                                                                                                      | boolean                                                                                                                      | -                                                    |          | 1.19     |
| useLabelForErrorMessage   | 是否使用 label 替换校验信息的 name 字段                                                                                                                                                             | boolean                                                                                                                      | -                                                    |          | 1.20     |
| preferMarginToDisplayHelp | 倾向使用 item 的 margin 空间来展示 help                                                                                                                                                             | boolean                                                                                                                      | false                                                |          | 1.26.37  |
| colon                     | 表示是否显示 label 后面的冒号                                                                                                                                                                       | boolean                                                                                                                      | false                                                |          | 1.22     |
| disabled                  | 是否禁用                                                                                                                                                                                            | boolean                                                                                                                      | false                                                |          | -        |

### Form.Item

手动传递了 wrapCol labelCol 会使用 Grid 辅助布局; labelAlign='top' 会强制禁用 Grid

| 参数                      | 说明                                                                                                   | 类型                                           | 默认值 | 是否必填 | 支持版本 |
| ------------------------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------- | ------ | -------- | -------- |
| labelCol                  | label 标签布局，同 `<Col>` 组件，设置 span offset 值，如 \{span: 8, offset: 16\}，该项仅在垂直表单有效 | ColProps                                       | -      |          | -        |
| wrapperCol                | 需要为输入控件设置布局样式时，使用该属性，用法同 labelCol                                              | ColProps                                       | -      |          | -        |
| help                      | 自定义提示信息，如不设置，则会根据校验规则自动生成。                                                   | ReactNode                                      | -      |          | -        |
| name                      | 字段名，默认赋值给第一个子元素                                                                         | string                                         | -      |          | -        |
| extra                     | 额外的提示信息，和 help 类似，当需要错误信息和提示文案同时出现时，可以使用这个。位于错误信息后面       | ReactNode                                      | -      |          | -        |
| validateState             | 校验状态，如不设置，则会根据校验规则自动生成                                                           | 'error' \| 'success' \| 'loading' \| 'warning' | -      |          | -        |
| hasFeedback               | 配合 validateState 属性使用，是否展示 success/loading 的校验状态图标，目前只有 Input 支持              | boolean                                        | false  |          | -        |
| children                  | node 或者 function(values)                                                                             | ReactNode \| ((values: FieldValues) => void)   | -      |          | -        |
| fullWidth                 | 单个 Item 中表单类组件宽度是否是 100%                                                                  | boolean                                        | -      |          | -        |
| labelAlign                | 标签的位置，如果不设置 labelCol 和 wrapperCol 那么默认是标签在上                                       | 'top' \| 'left' \| 'inset'                     | -      |          | -        |
| labelTextAlign            | 标签的左右对齐方式                                                                                     | 'left' \| 'right'                              | -      |          | -        |
| required                  | [表单校验] 不能为空                                                                                    | boolean                                        | -      |          | -        |
| asterisk                  | required 的星号是否显示                                                                                | boolean                                        | -      |          | -        |
| requiredMessage           | required 自定义错误信息                                                                                | string                                         | -      |          | -        |
| requiredTrigger           | required 自定义触发方式，默认值 onChange, 原生事件均可使用 onChange/onBlur/onFocus/...                 | string \| Array\<string>                       | -      |          | -        |
| min                       | [表单校验] 最小值                                                                                      | number                                         | -      |          | -        |
| max                       | [表单校验] 最大值                                                                                      | number                                         | -      |          | -        |
| minmaxMessage             | min/max 自定义错误信息                                                                                 | string                                         | -      |          | -        |
| minmaxTrigger             | min/max 自定义触发方式                                                                                 | string \| Array\<string>                       | -      |          | -        |
| minLength                 | [表单校验] 字符串最小长度 / 数组最小个数                                                               | number                                         | -      |          | -        |
| maxLength                 | [表单校验] 字符串最大长度 / 数组最大个数                                                               | number                                         | -      |          | -        |
| minmaxLengthMessage       | minLength/maxLength 自定义错误信息                                                                     | string                                         | -      |          | -        |
| minmaxLengthTrigger       | minLength/maxLength 自定义触发方式                                                                     | string \| Array\<string>                       | -      |          | -        |
| length                    | [表单校验] 字符串精确长度 / 数组精确个数                                                               | number                                         | -      |          | -        |
| lengthMessage             | length 自定义错误信息                                                                                  | string                                         | -      |          | -        |
| lengthTrigger             | length 自定义触发方式                                                                                  | string \| Array\<string>                       | -      |          | -        |
| pattern                   | 正则校验                                                                                               | unknown                                        | -      |          | -        |
| patternMessage            | pattern 自定义错误信息                                                                                 | string                                         | -      |          | -        |
| patternTrigger            | pattern 校验何时触发，默认值 onChange, 原生事件均可使用 onChange/onBlur/onFocus/...                    | string \| Array\<string>                       | -      |          | -        |
| format                    | [表单校验] 四种常用的 pattern                                                                          | 'number' \| 'email' \| 'url' \| 'tel'          | -      |          | -        |
| formatMessage             | format 自定义错误信息                                                                                  | string                                         | -      |          | -        |
| formatTrigger             | format 校验何时触发，默认值 onChange, 原生事件均可使用 onChange/onBlur/onFocus/...                     | string \| Array\<string>                       | -      |          | -        |
| validator                 | [表单校验] 自定义校验函数                                                                              | Validator                                      | -      |          | -        |
| validatorTrigger          | validator 自定义触发方式，默认值 onChange, 原生事件均可使用 onChange/onBlur/onFocus/...                | string \| Array\<string>                       | -      |          | -        |
| autoValidate              | 是否修改数据时自动触发校验                                                                             | boolean                                        | -      |          | -        |
| device                    | 预设屏幕宽度                                                                                           | 'desktop' \| 'phone' \| 'tablet'               | -      |          | -        |
| colSpan                   | 在响应式布局模式下，表单项占多少列                                                                     | number                                         | -      |          | -        |
| labelWidth                | 在响应式布局下，且 label 在左边时，label 的宽度是多少                                                  | number \| string                               | 100    |          | -        |
| isPreview                 | 是否开启预览态                                                                                         | boolean                                        | -      |          | -        |
| renderPreview             | 预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 根据包裹的组件的 value 类型而决定 | (values: unknown) => unknown                   | -      |          | -        |
| errorMessageName          | 替代校验信息的 name 字段，useLabelForErrorMessage 开启的情况下比 label 优先级高                        | string                                         | -      |          | -        |
| useLabelForErrorMessage   | 是否使用 label 替换校验信息的 name 字段                                                                | boolean                                        | -      |          | -        |
| preferMarginToDisplayHelp | 倾向使用 item 的 margin 空间来展示 help                                                                | boolean                                        | false  |          | 1.26.37  |
| colon                     | 表示是否显示 label 后面的冒号                                                                          | boolean                                        | -      |          | -        |
| disabled                  | 是否禁用表单                                                                                           | boolean                                        | -      |          | -        |
| valueName                 | 子元素的 value 名称                                                                                    | string                                         | -      |          | -        |
| type                      | 表单类型                                                                                               | string                                         | -      |          | -        |

### Form.Submit

继承 Button API

| 参数     | 说明                                                                                                       | 类型                                                           | 默认值    | 是否必填 |
| -------- | ---------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | --------- | -------- |
| onClick  | 点击提交后触发<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 数据<br/>_errors_: 错误数据<br/>_field_: 实例 | (value?: unknown, errors?: unknown, field?: NextField) => void | func.noop |          |
| validate | 是否校验/需要校验的 name 数组                                                                              | boolean \| Array\<string>                                      | -         |          |
| field    | 自定义 field (在 Form 内不需要设置)                                                                        | NextField                                                      | -         |          |

### Form.Reset

继承 Button API

| 参数      | 说明                                | 类型           | 默认值    | 是否必填 |
| --------- | ----------------------------------- | -------------- | --------- | -------- |
| names     | 自定义重置的字段                    | Array\<string> | -         |          |
| onClick   | 点击提交后触发                      | () => void     | func.noop |          |
| toDefault | 返回默认值                          | boolean        | -         |          |
| field     | 自定义 field (在 Form 内不需要设置) | NextField      | -         |          |

### Form.Error

自定义错误展示

| 参数     | 说明                                                     | 类型                                                                  | 默认值 | 是否必填 |
| -------- | -------------------------------------------------------- | --------------------------------------------------------------------- | ------ | -------- |
| name     | 表单名                                                   | string \| Array\<string>                                              | -      |          |
| field    | 自定义 field (在 Form 内不需要设置)                      | NextField                                                             | -      |          |
| children | 自定义错误渲染，可以是 node 或者 function(errors, state) | ReactNode \| ((errors: errorsGroup, state?: FieldState) => ReactNode) | -      |          |


---


## grid

# zh-CN order=13

# 无障碍键盘操作指南

默认 `<Row>` 和 `<Col>` 会加上 `role="row"` 和 `role="gridcell"`, 但是为了完美的无障碍实现, 开发者还应该在外部容器加上 `role="grid"`。

---

# en-US order=13

# Accessibility

Use `role="grid"` to reach better accessibility.


---


## grid

# zh-CN order=10

# 多列垂直方向对齐方式

（不支持 IE9 浏览器）基于 Flex 的 align-items 和 align-self 属性实现，在 `Row` 上设置 `align` 属性，即可控制 `Row` 下面所有 `Col` 的垂直方向对齐方式：top（顶部对齐，默认），center（居中对齐），bottom（底部对齐），baseline（第一行文字的基线对齐），stretch（如果未设置高度或设为 auto，将占满整个容器的高度）；在 `Col` 上设置 `align` 属性，可允许它与其它列不一样的对齐方式，覆盖 `Row` 的 `align` 属性。

---

# en-US order=10

# Vertical alignment of columns

(IE9 is not supported) Based on Flex's align-items and align-self attributes, set the `align` property on `Row` to control the vertical alignment of all `Col` below `Row`: top (top alignment, default), center (center alignment), bottom (bottom alignment), baseline (baseline alignment of the first line of text), stretch (if no height is set or set to auto, it will fill the height of the entire container); set the `align` property on `Col`, it can override the `align` property of `Row`.


---


## grid

# zh-CN order=0

# 基础布局

通过 `Col` 的 `span` 属性指定该列宽度占整行宽度24分之几或5分之几。

---

# en-US order=0

# Basic layout

Use the `span` property of `Col` to specify the width of the column.


---


## grid

# zh-CN order=5

# 响应式布局

类似 Bootstrap 的响应式设计，预设6个响应尺寸：xxs(320px), xs(480px), s(720px), m(990px), l(1200px), xl(1500px)。

---

# en-US order=5

# Responsive layout

Similar to Bootstrap's responsive design, it presets six response sizes: xxs (320px), xs (480px), s (720px), m (990px), l (1200px), and xl (1500px).


---


## grid

# zh-CN order=12

# 自定义元素渲染类型

使用 `component` 来指定需要渲染的元素类型，默认为 `div`

---

# en-US order=12

# Customize rendered type of the element

Use `component` property to customize rendered type of the element.


---


## grid

# zh-CN order=1

# 固定宽度列

通过 `Col` 的 `fixedSpan` 属性来指定某列为固定宽度列，其宽度的计算方式为 20 \* fixedSpan。

---

# en-US order=1

# Fixed width column

The `fixedSpan` property of `Col` specifies a column as a fixed-width column whose width is calculated as 20 \* fixedSpan.


---


## grid

# zh-CN order=2

# 列间距

列与列间距默认为0，可以通过设置 `Row` 的 `gutter` 属性来改变列间距。

---

# en-US order=2

# Columns spacing

The spacing of the columns defaults to 0. You can change the column spacing by setting the `gutter` property of `Row`.


---


## grid

# zh-CN order=6

# 显示与隐藏

提供了强大的响应式的显示与隐藏功能，支持在不同断点下的显示与隐藏。

---

# en-US order=6

# Display and hide

Provides a powerful responsive display and hide functionality under different breakpoints.


---


## grid

# zh-CN order=11

# 多列水平方向对齐方式

（不支持 IE9 浏览器）基于 Flex 的 justify-content 属性实现，在 `Row` 上设置 `justify` 属性，即可行内多列水平方向对齐方式：start（左对齐，默认），center（居中对齐），end（右对齐），space-between（两端对齐，项目之间的间隔都相），space-around（两侧的间隔相等，列之间的间隔比列与左右两端的间隔大一倍）。

---

# en-US order=11

# Horizontal alignment of columns

(IE9 is not supported) Based on Flex's justify-content attributes, set the `justify` property on `Row` to control the horizontal alignment: start (left-aligned, default), center (center-aligned),end (right-aligned), space-between (both-aligned, spacing between items are all the same), space-around (equal intervals on both sides, the spacing between columns is double the spacing between the column and the left and right ends).


---


## grid

# zh-CN order=4

# 嵌套布局

`Col` 下也可嵌套 `Row`，以完成更细致的布局。

---

# en-US order=4

# Nested layout

`Row` can also be nested under `Col` to create a more detailed layout.


---


## grid

# zh-CN order=8

# 偏移

（不支持 IE9 浏览器）列可以向右偏移一定距离，该距离的计算方式和列所占宽度计算方式相同。

---

# en-US order=8

# Offset

(IE9 is not supported) Column can be offset to the right by a distance that is calculated in the same way as a column.


---


## grid

# zh-CN order=9

# 固定宽度偏移

（不支持 IE9 浏览器）列可以向右偏移一定距离，该距离的计算方式和固定宽度列的宽度相同。

---

# en-US order=9

# Fixed offset

(IE9 is not supported) Column can be offset to the right by a fixed distance that is calculated in the same way as a fixed-width column.


---


## grid

# zh-CN order=7

# 设置行的宽度

默认 `Row` 的宽度被设置为100%，可以通过设置 `fixed` 属性为 true，来让 `Row` 的宽度不立刻随着是视口大小变动而变动，而是在某个断点下维持固定的宽度，也可以通过设置 `fixedWidth` 属性为某一断点值，从而固定 `Row` 的宽度，不再随着视口大小变动而变动。

---

# en-US order=7

# Set the width of the row

The default width of the `Row` is set to 100%. You can set the `fixed` property to true so that the width of `Row` does not immediately change with the size of the viewport. Instead, it is maintained at a certain breakpoint. You can also set the `fixedWidth` property to a certain breakpoint value, thus fixing the width of `Row`, no longer changing with the size of the viewport.


---


## grid

# zh-CN order=3

# 溢出后是否换行

（不支持 IE9 浏览器）默认列在行中宽度溢出后不会换行，如果想自动换行，请为 `Row` 设置 `wrap` 为 true。

---

# en-US order=3

# Wrap while overflow

(IE9 is not supported) Default the column is no longer wrapped when the width overflows. If you want to wrap automatically, set `wrap` of `Row` to true.


---


## grid

# Grid

-   category: Components
-   family: General
-   chinese: 栅格
-   type: 布局
-   cols: 1

---

栅格组件。

## 如何使用

-   此栅格系统提供了320，480，720, 990，1200，1500等几乎所有主流分辨率场景的响应规则。
-   响应式栅格采用24列栅格体系和5分比实现，以满足2，3，4，5，6分比布局等多种情况。
-   固定栅格采用 20px 宽度作为单位栅格， 推荐使用9，10，12，14，16，18，24，但同时也提供了从1到30的所有栅格，也可根据需求定制固定栅格列。
-   响应式断点阈值为：xss(320px), xs(480px), s(720px), m(990px), l(1200px), xl(1500px)。
-   基于Flex实现，对 IE9 通过 `display:table;` 兼容实现，但 IE9 仅支持基本的响应式布局（详情请参考 API 和 DEMO 的说明）。

## API

### Grid

### Row

| 参数       | 说明                                                         | 类型                                                              | 默认值 | 是否必填 |
| ---------- | ------------------------------------------------------------ | ----------------------------------------------------------------- | ------ | -------- |
| children   | 行内容                                                       | React.ReactNode                                                   | -      |          |
| gutter     | 列间隔                                                       | string \| number                                                  | 0      |          |
| wrap       | 列在行中宽度溢出后是否换行                                   | boolean                                                           | false  |          |
| fixed      | 行在某一断点下宽度是否保持不变（默认行宽度随视口变化而变化） | boolean                                                           | false  |          |
| fixedWidth | 固定行的宽度为某一断点的宽度，不受视口影响而变动             | BreakPoints                                                       | -      |          |
| align      | （不支持IE9浏览器）多列垂直方向对齐方式                      | 'top' \| 'center' \| 'bottom' \| 'baseline' \| 'stretch'          | -      |          |
| justify    | （不支持IE9浏览器）行内具有多余空间时的布局方式              | 'start' \| 'center' \| 'end' \| 'space-between' \| 'space-around' | -      |          |
| hidden     | 行在不同断点下的显示与隐藏                                   | boolean \| string \| Array\<BreakPoints>                          | -      |          |
| component  | 指定以何种元素渲染该节点                                     | string \| FunctionComponent\<unknown> \| ComponentClass\<unknown> | 'div'  |          |

### Row.Col

| 参数        | 说明                                                                                                     | 类型                                                     | 默认值 | 是否必填 |
| ----------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- | ------ | -------- |
| children    | 列内容                                                                                                   | React.ReactNode                                          | -      |          |
| span        | 列宽度                                                                                                   | string \| number                                         | -      |          |
| fixedSpan   | 固定列宽度                                                                                               | string \| number                                         | -      |          |
| offset      | （不支持IE9浏览器）列偏移                                                                                | string \| number                                         | -      |          |
| fixedOffset | （不支持IE9浏览器）固定列偏移，宽度值为20 \* 栅格数\<br\>\<br\>**可选值**:\<br\>1, 2, 3, ..., 28, 29, 30 | string \| number                                         | -      |          |
| align       | （不支持IE9浏览器）多列垂直方向对齐方式，可覆盖Row的align属性                                            | 'top' \| 'center' \| 'bottom' \| 'baseline' \| 'stretch' | -      |          |
| hidden      | 列在不同断点下的显示与隐藏                                                                               | boolean \| string \| Array\<BreakPoints>                 | -      |          |
| xxs         | \>=320px，响应式栅格                                                                                     | string \| number \| PointProps                           | -      |          |
| xs          | \>=480px，响应式栅格                                                                                     | string \| number \| PointProps                           | -      |          |
| s           | \>=720px，响应式栅格                                                                                     | string \| number \| PointProps                           | -      |          |
| m           | \>=990px，响应式栅格                                                                                     | string \| number \| PointProps                           | -      |          |
| l           | \>=1200px，响应式栅格                                                                                    | string \| number \| PointProps                           | -      |          |
| xl          | \>=1500px，响应式栅格                                                                                    | string \| number \| PointProps                           | -      |          |
| component   | 指定以何种元素渲染该节点，默认为 'div'                                                                   | Ele \| (() => Ele) \| string                             | 'div'  |          |


---


## icon

# zh-CN order=6

# 无障碍支持

若为装饰性icon，请设置通过设置 `aria-hidden` 忽略；若为按钮类型icon，请务必设置 `role="button"` 和 `aria-label`。

# en-US order=6

# Accessibility

If it's a decorative icon, set `aria-hidden` to ignore; Or it's a button, set `role="button" `and `aria-label`.


---


## icon

# zh-CN order=1

# 基本用法

展示图标基本使用方法。

# en-US order=0

# Basic Usage

Basic usage of Icon。


---


## icon

# zh-CN order=5

# 使用其他源的图标

直接使用 iconfont 源扩展icon，且不使用定制主题包的方式，支持svg图标

# en-US order=5

# Extend icon

Extend icon without theme package


---


## icon

# zh-CN order=2

# 尺寸

ICON的尺寸包括：`xxs`，`xs`，`small`，`medium`，`large`，`xl`，`xxl`，`xxxl`, `inherit`。

# en-US order=2

# Size

ICON's sizes include:`xxs`，`xs`，`small`，`medium`，`large`，`xl`，`xxl`，`xxxl`, `inherit`。


---


## icon

# zh-CN order=3

# 自定义样式

图标字体本质上还是文字，可以使用 style 和 className 设置图标的大小和颜色。

# en-US order=3

# Custom Style

Icon fonts are essentially text. You can use `style` and `className` to set the size and color of the icons.


---


## icon

# zh-CN order=0

# 图标列表

点击图标复制代码。

# en-US order=1

# List of Icons

Click on the icon to copy the code.


---


## icon

# Icon

-   category: Components
-   family: General
-   chinese: 图标
-   type: 展示
-   cols: 1

---

## API

### Icon

| 参数   | 说明                                                                                 | 类型          | 默认值      |
| ---- | ---------------------------------------------------------------------------------- | ----------- | -------- |
| size | 指定图标大小<br/><br/>**可选值**<br/> xxs, xs, small, medium, large, xl, xxl, xxxl, inherit | Enum/Number | 'medium' |
| type | 指定显示哪种图标                                                                           | String      | -        |

<!-- api-extra-start -->

### Icon.createFromIconfontCN

通过自定义 iconfont源来使用使用svg格式的图片，默认有缓存处理

```js
import { Icon } from '@alifd/next';

const CustomIcon = Icon.createFromIconfontCN({
    scriptUrl: '//at.alicdn.com/t/font_1464085_egnk4s8yv2f.js',
});

// 同 Icon 基础元素一样，有相同的 size 设定
ReactDOM.render(
    <div>
        <CustomIcon type="icon-store" size="small"/>
        <CustomIcon type="icon-gift"/>
        <CustomIcon type="icon-pic" size="large"/>
    </div>
, mountNode);
```

<!-- api-extra-end -->

## FAQ

### 如何添加自定义Icon？

默认提供部分基础 icon ，若要添加自定义 icon 可在 Fusion 设计中心新建主题，编辑主题中的Icon组件，完成后发布主题。每个主题是一个 npm 包，npm 包里面包含了主题变量、iconfont 地址等相关代码。在你的项目里引用该自定义主题包，更新主题包的版本即可（前提是你的项目/构建工具支持 Fusion 主题的使用）

## 无障碍键盘操作指南

-   Icon无键盘操作；
-   若为装饰性icon，请设置通过设置 `aria-hidden` 忽略；若为按钮类型icon，请务必设置 `role="button"` 和 `aria-label`


---


## input

# zh-CN order=13

# 无障碍支持

通过`aria-label`对`Input`组件进行描述。关于键盘操作请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=13

# Accessibility

Describe the `Input` component by `aria-label`.Please refer to `ARIA and KeyBoard` for keyboard operation.


---


## input

# zh-CN order=2

# 前后扩展

# en-US order=2

# Addon


---


## input

# zh-CN order=9

# 自动高度

根据内容自动调整 TextArea 的高度

# en-US order=9

# Auto Height

auto set TextArea height by content


---


## input

# zh-CN order=0

# 简单

# en-US order=0

# Basic


---


## input

# zh-CN order=3

# 清除按钮

通过设置 hasClear 添加清除按钮.

hint为水印按钮，和hasClear占用同一个地方配合使用

# en-US order=3

# Clear Button


---


## input

# zh-CN order=7

# 禁用状态

为 `Input` 设置 `disabled` 状态；

# en-US order=7

# Disabled state

Set `Input` as `disabled` state


---


## input

# zh-CN order=11

# 输入框组合

Group 具有两边长度固定中间组件任意伸缩的能力。在Input中可以用addonBefore/addonAfter快速使用

# en-US order=11

# Input Groups

Group has an ability that total lenght is definite and its inner input is flexible.


---


## input

# zh-CN order=12

# 中文输入法

中文输入完成的时候才会触发 onChange

# en-US order=0

# ime

trigger onChange after IME finished


---


## input

# zh-CN order=8

# 水印和前后缀

可以添加水印， 为input前后端增加额外内容

# en-US order=8

# Watermark/Prefix/Suffix

Add Watermark/Prefix/Suffix for Input


---


## input

# zh-CN order=5

# 最大长度

最大长度 showLimitHint 会展现限制数字; cutString 可控制是否要切割字符串, 用于只展示最大长度

# en-US order=5

# Addon

the prop `showLimitHint` will limit the number of characters


---


## input

# zh-CN order=1

# 密码输入框

设置 `Input` 为 密码类型；

# en-US order=1

# Password Input

Set `Input` as a password type input;


---


## input

# zh-CN order=4

# 错误状态

为 `Input` 设置 `error` 状态；

# en-US order=4

# Error State

Set Error State for Input


---


## input

# zh-CN order=12

# 自定义样式

通过style设置宽度

# en-US order=12

# Custom Style

Custom style can be set using param `style`.


---


## input

# zh-CN order=6

# 去除空格

onChange返回会自动去除头尾空字符

# en-US order=6

# Auto Trim

onChange callback will return the trimmed text value


---


## input

# Input

-   category: Components
-   family: DataEntry
-   chinese: 输入框
-   type: 表单

---

表单输入组件。

## 何时使用

表单输入，一般配合 Form 使用。

-   Input 不支持 Number 类型数字，如有需要使用 NumberPicker 支持数字选择
-   `1.23` 版本新增了 API `composition` , 开启后可以在输入法结束后再触发 onChange（包括中文输入法、日语输入法等）

## API

### Input

| 参数                 | 说明                                                            | 类型                                                                                                                                                                                                                       | 默认值   | 是否必填 | 支持版本 |
| -------------------- | --------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------- | -------- |
| value                | 当前值（受控）                                                  | string \| number                                                                                                                                                                                                           | -        |          | -        |
| defaultValue         | 默认值（非受控）                                                | string \| number                                                                                                                                                                                                           | -        |          | -        |
| onChange             | 发生改变的时候触发的回调                                        | (<br/> value: string \| number,<br/> e:<br/> \| React.ChangeEvent\<HTMLInputElement><br/> \| React.CompositionEvent\<HTMLInputElement><br/> \| React.KeyboardEvent\<HTMLInputElement>,<br/> reason?: string<br/> ) => void | -        |          | -        |
| onKeyDown            | 键盘按下的时候触发的回调                                        | (<br/> e: React.KeyboardEvent\<HTMLInputElement>,<br/> opts: OnKeyDownOpts<br/> ) => void                                                                                                                                  | -        |          | -        |
| disabled             | 禁用状态                                                        | boolean                                                                                                                                                                                                                    | false    |          | -        |
| maxLength            | 最大长度                                                        | number                                                                                                                                                                                                                     | -        |          | -        |
| hasLimitHint         | 是否展现最大长度样式                                            | boolean                                                                                                                                                                                                                    | false    |          | -        |
| showLimitHint        | 是否展现最大长度样式                                            | boolean                                                                                                                                                                                                                    | false    |          | -        |
| cutString            | 当设置了 maxLength 时，是否截断超出的字符串                     | boolean                                                                                                                                                                                                                    | true     |          | -        |
| readOnly             | 只读                                                            | boolean                                                                                                                                                                                                                    | false    |          | -        |
| trim                 | onChange 返回会自动去除头尾空字符                               | boolean                                                                                                                                                                                                                    | false    |          | -        |
| placeholder          | 输入提示                                                        | string                                                                                                                                                                                                                     | -        |          | -        |
| onFocus              | 获取焦点时候触发的回调                                          | (e: React.FocusEvent\<HTMLInputElement>) => void                                                                                                                                                                           | -        |          | -        |
| onBlur               | 失去焦点时候触发的回调                                          | (e: React.FocusEvent\<HTMLInputElement>) => void                                                                                                                                                                           | -        |          | -        |
| getValueLength       | 自定义字符串计算长度方式                                        | (value: string) => number \| void                                                                                                                                                                                          | -        |          | -        |
| className            | 自定义 class                                                    | string                                                                                                                                                                                                                     | -        |          | -        |
| style                | 自定义内联样式                                                  | React.CSSProperties                                                                                                                                                                                                        | -        |          | -        |
| htmlType             | 原生 type                                                       | string                                                                                                                                                                                                                     | -        |          | -        |
| name                 | name                                                            | string                                                                                                                                                                                                                     | -        |          | -        |
| state                | 状态                                                            | 'error' \| 'loading' \| 'success' \| 'warning'                                                                                                                                                                             | -        |          | -        |
| label                | label                                                           | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| hasClear             | 是否出现 clear 按钮                                             | boolean                                                                                                                                                                                                                    | -        |          | -        |
| hasBorder            | 是否有边框                                                      | boolean                                                                                                                                                                                                                    | true     |          | -        |
| size                 | 尺寸                                                            | 'small' \| 'medium' \| 'large'                                                                                                                                                                                             | 'medium' |          | -        |
| onPressEnter         | 按下回车的回调                                                  | (e: React.KeyboardEvent\<HTMLInputElement>) => void                                                                                                                                                                        | -        |          | -        |
| hint                 | 水印 (Icon 的 type 类型，和清除按钮占用同一个地方)              | string \| React.ReactNode                                                                                                                                                                                                  | -        |          | -        |
| innerBefore          | 文字前附加内容                                                  | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| innerAfter           | 文字后附加内容                                                  | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| addonBefore          | 输入框前附加内容                                                | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| addonAfter           | 输入框后附加内容                                                | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| addonTextBefore      | 输入框前附加文字                                                | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| addonTextAfter       | 输入框后附加文字                                                | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| autoComplete         | 自动补全 (原生 input 支持)                                      | string                                                                                                                                                                                                                     | 'off'    |          | -        |
| autoFocus            | 自动聚焦 (原生 input 支持)                                      | boolean                                                                                                                                                                                                                    | -        |          | -        |
| isPreview            | 是否为预览态                                                    | boolean                                                                                                                                                                                                                    | false    |          | -        |
| renderPreview        | 自定义预览态内容                                                | (value: string \| number \| undefined, props: InputProps) => React.ReactNode                                                                                                                                               | -        |          | -        |
| composition          | 开启后会过滤输入法中间字母状态，文字输入完成后才会触发 onChange | boolean                                                                                                                                                                                                                    | false    |          | 1.23     |
| hoverShowClear       | hover 展示 clear (配合 hasClear=true 使用)                      | boolean                                                                                                                                                                                                                    | false    |          | 1.24     |
| extra                | 额外内容                                                        | React.ReactNode                                                                                                                                                                                                            | -        |          | -        |
| htmlSize             | 原生 input 的 size 属性                                         | string                                                                                                                                                                                                                     | -        |          | -        |
| inputRender          | 自定义 input 样式                                               | (input: React.ReactElement) => React.ReactNode                                                                                                                                                                             | -        |          | -        |
| inputStyle           | 自定义 input 样式                                               | React.CSSProperties                                                                                                                                                                                                        | -        |          | -        |
| inputClassName       | 自定义 input 类名                                               | string                                                                                                                                                                                                                     | -        |          | -        |
| innerBeforeClassName | 文字前附加内容类名                                              | string                                                                                                                                                                                                                     | -        |          | -        |
| innerAfterClassName  | 文字后附加内容类名                                              | string                                                                                                                                                                                                                     | -        |          | -        |

### Input.TextArea

| 参数           | 说明                                                            | 类型                                                                                         | 默认值   | 是否必填 | 支持版本 |
| -------------- | --------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------- | -------- | -------- |
| value          | 当前值（受控）                                                  | string \| number                                                                             | -        |          | -        |
| defaultValue   | 默认值（非受控）                                                | string \| number                                                                             | -        |          | -        |
| onChange       | 发生改变的时候触发的回调                                        | (value: string, e: React.ChangeEvent\<HTMLTextAreaElement>, type?: string) => void           | -        |          | -        |
| onKeyDown      | 键盘按下的时候触发的回调                                        | (<br/> e: React.KeyboardEvent\<HTMLTextAreaElement>,<br/> opts: OnKeyDownOpts<br/> ) => void | -        |          | -        |
| disabled       | 禁用状态                                                        | boolean                                                                                      | false    |          | -        |
| maxLength      | 最大长度                                                        | number                                                                                       | -        |          | -        |
| hasLimitHint   | 是否展现最大长度样式                                            | boolean                                                                                      | false    |          | -        |
| showLimitHint  | 是否展现最大长度样式                                            | boolean                                                                                      | false    |          | -        |
| cutString      | 当设置了 maxLength 时，是否截断超出的字符串                     | boolean                                                                                      | true     |          | -        |
| readOnly       | 只读                                                            | boolean                                                                                      | false    |          | -        |
| trim           | onChange 返回会自动去除头尾空字符                               | boolean                                                                                      | false    |          | -        |
| placeholder    | 输入提示                                                        | string                                                                                       | -        |          | -        |
| onFocus        | 获取焦点时候触发的回调                                          | (e: React.FocusEvent\<HTMLTextAreaElement>) => void                                          | -        |          | -        |
| onBlur         | 失去焦点时候触发的回调                                          | (e: React.FocusEvent\<HTMLTextAreaElement>) => void                                          | -        |          | -        |
| getValueLength | 自定义字符串计算长度方式                                        | (value: string) => number \| void                                                            | -        |          | -        |
| className      | 自定义 class                                                    | string                                                                                       | -        |          | -        |
| style          | 自定义内联样式                                                  | React.CSSProperties                                                                          | -        |          | -        |
| htmlType       | 原生 type                                                       | string                                                                                       | -        |          | -        |
| name           | name                                                            | string                                                                                       | -        |          | -        |
| state          | 状态                                                            | 'error' \| 'warning' \| 'loading'                                                            | -        |          | -        |
| hasBorder      | 是否有边框                                                      | boolean                                                                                      | true     |          | -        |
| autoHeight     | 根据内容自动改变高度                                            | boolean \| { minRows?: number \| string; maxRows?: number \| string }                        | false    |          | -        |
| rows           | 多行文本框高度                                                  | number                                                                                       | 4        |          | -        |
| isPreview      | 是否为预览态                                                    | boolean                                                                                      | false    |          | -        |
| renderPreview  | 自定义预览态内容                                                | (value: string \| number \| undefined, props: TextAreaProps) => React.ReactNode              | -        |          | -        |
| composition    | 开启后会过滤输入法中间字母状态，文字输入完成后才会触发 onChange | boolean                                                                                      | false    |          | 1.23     |
| hasClear       | 是否出现 clear 按钮                                             | boolean                                                                                      | -        |          | -        |
| size           | 尺寸                                                            | 'small' \| 'medium' \| 'large'                                                               | 'medium' |          | -        |

### Input.Group

| 参数                 | 说明                   | 类型            | 默认值 | 是否必填 |
| -------------------- | ---------------------- | --------------- | ------ | -------- |
| addonBefore          | 输入框前附加内容       | React.ReactNode | -      |          |
| addonBeforeClassName | 输入框前附加内容的类名 | string          | -      |          |
| addonAfter           | 输入框后附加内容       | React.ReactNode | -      |          |
| addonAfterClassName  | 输入框后附加内容的类名 | string          | -      |          |
| rtl                  | rtl                    | boolean         | -      |          |
| disabled             | 禁用状态               | boolean         | -      |          |

### Input.Password

继承 Input 的属性

| 参数       | 说明             | 类型    | 默认值 | 是否必填 |
| ---------- | ---------------- | ------- | ------ | -------- |
| showToggle | 是否展示切换按钮 | boolean | true   |          |

### OnKeyDownOpts

| 参数          | 说明             | 类型    | 默认值 | 是否必填 |
| ------------- | ---------------- | ------- | ------ | -------- |
| beTrimed      | 输入的空格被清理 | boolean | -      |          |
| overMaxLength | 已超出最大长度   | boolean | -      |          |

## Input/TextArea 内部函数 (通过 refs 获取)

| 参数         | 说明                                                                                                                                             | 类型     | 默认值 |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------- | ------ |
| getInputNode | 获取真正 input 节点                                                                                                                              | Function |        |
| focus        | 获取焦点<br><br>**签名**:<br> Function(start:Number, end: Number)<br>**参数**:<br>_start_: {Number} 光标起始位置<br>_end_: {Number} 选择结束位置 | Function |        |

## 无障碍键盘操作指南

| 按键  | 说明                |
| :---- | :------------------ |
| Enter | 触发 onKeyDown 事件 |
| Any   | 触发 onChange 事件  |


---


## list

# zh-CN order=0

# 基础列表

最简单的用法。

# en-US order=0

# Basic Usage

Simple usage of List component.


---


## list

# zh-CN order=1

# 图文列表

图文列表展示。

# en-US order=1

# Basic Usage

Complex usage of List component.


---


## list

# zh-CN order=3

# 自定义 loading

自定义 `loading` 样式。

# en-US order=3

# Basic Usage

Custom Loading component.


---


## list

# zh-CN order=4

# 自定义空内容

自定义无数据时展示的内容。

# en-US order=4

# Basic Usage

Custom empty content.


---


## list

# zh-CN order=2

# 带 loading 的列表

带 `loading` 的列表展示。

# en-US order=2

# Basic Usage

List width loading.


---


## list

# List

-   category: Components
-   family: DataDisplay
-   chinese: 列表
-   type: 展示

---

列表组件，1.19.4+ 版本支持。

## 何时使用

最基础的列表展示，可承载文字、列表、图片、段落。

## API

### List

| 参数             | 说明                                                                                                                                                                                                  | 类型                                               | 默认值   | 是否必填 |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- | -------- | -------- |
| header           | 列表头部                                                                                                                                                                                              | ReactNode                                          | -        |          |
| footer           | 列表尾部                                                                                                                                                                                              | ReactNode                                          | -        |          |
| size             | 列表尺寸                                                                                                                                                                                              | 'medium' \| 'small'                                | 'medium' |          |
| divider          | 是否显示分割线                                                                                                                                                                                        | boolean                                            | true     |          |
| children         | children                                                                                                                                                                                              | ReactNode                                          | -        |          |
| dataSource       | 列表项数据源                                                                                                                                                                                          | DataItem[]                                         | -        |          |
| renderItem       | 当使用 dataSource 时，可以用 renderItem 自定义渲染列表项<br/><br/>**签名**:<br/>**参数**:<br/>_current_: 当前遍历的项<br/>_index_: 当前遍历的项的索引<br/>**返回值**:<br/>- 自定义渲染的 ReactElement | (current: DataItem, index: number) => ReactElement | -        |          |
| loading          | loading 状态控制                                                                                                                                                                                      | boolean                                            | false    |          |
| loadingComponent | 自定义 Loading 组件<br/><br/>**签名**:<br/>**参数**:<br/>_props_: 透传 props<br/>**返回值**:<br/>- 自定义的 Loading 组件                                                                              | (props: LoadingProps) => ReactElement              | -        |          |
| emptyContent     | 当列表为空时显示的内容                                                                                                                                                                                | ReactNode                                          | -        |          |

### List.Item

| 参数        | 说明                             | 类型      | 默认值 | 是否必填 |
| ----------- | -------------------------------- | --------- | ------ | -------- |
| title       | 列表元素的标题                   | ReactNode | -      |          |
| description | 列表元素的描述内容               | ReactNode | -      |          |
| media       | 列表元素的头像 / 图标 / 图片内容 | ReactNode | -      |          |
| extra       | 额外内容                         | ReactNode | -      |          |


---


## loading

# zh-CN order=6

# 无障碍支持

默认支持通过按下`Esc`键退出全屏显示加载态。

# en-US order=6

# Accessibility

Press `Esc` to exit fullScreen loading.


---


## loading

# zh-CN order=0

# 基本

简单的 Loading 状态，包裹需要显示加载态的组件。

# en-US order=0

# Basic Usage

a basic way to use it.


---


## loading

# zh-CN order=5

# 全屏

通过`fullScreen`强制全屏显示加载态，通过`safeNode`指定安全节点。

# en-US order=5

# Fullscreen

display a fullscreen loading


---


## loading

# zh-CN order=3

# 自定义动画指示符

通过`indicator`自定义动画指示符，传入动画元素。

# en-US order=3

# Custom Animation Indicator

Use custom animation indicator.


---


## loading

# zh-CN order=1

# 动画尺寸

通过`size`设置Loading动画的尺寸，只对原生的动画指示符`indicator`有效。

# en-US order=1

# Animation Size

Sets Loading animation size. It only works for default loading animation.


---


## loading

# zh-CN order=4

# 受控关闭加载

通过`visible`受控显示或关闭加载动画。

# en-US order=4

# Loading State

Loading state can be toggle by `visible`。


---


## loading

# zh-CN order=2

# 自定义提示语及其位置

通过`tip`自定义加载提示语，通过`tipAlign`设置提示语的位置，目前支持 `right` / `bottom (default)`。

# en-US order=2

# Custom Tip Position

Use custom loading tip with its location.


---


## loading

# Loading

-   category: Components
-   family: Feedback
-   chinese: 加载
-   type: 基本

---

加载组件，用于页面和区块的加载中状态。

## 何时使用

页面局部处于等待异步数据或正在渲染过程时，合适的加载动效会有效缓解用户的焦虑。

## 如何使用

Loading 默认使用 `display='inline-block'` 布局的方式包裹内部元素。

如果希望**通栏包裹**， 可以修改 `<Loading style={{display: 'block'}} />`。

## API

### Loading

| 参数            | 说明                                                                                                                                                                                                        | 类型                                        | 默认值   | 是否必填 |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- | -------- | -------- |
| tip             | 自定义内容，可以传入 string 或 reactElement                                                                                                                                                                 | React.ReactNode \| string                   | -        |          |
| tipAlign        | 自定义内容位置                                                                                                                                                                                              | 'right' \| 'bottom'                         | 'bottom' |          |
| visible         | loading 状态, 默认 true                                                                                                                                                                                     | boolean                                     | true     |          |
| size            | 设置动画尺寸                                                                                                                                                                                                | 'large' \| 'medium'                         | 'large'  |          |
| indicator       | 自定义动画                                                                                                                                                                                                  | React.ReactNode                             | -        |          |
| color           | 动画颜色                                                                                                                                                                                                    | string                                      | -        |          |
| fullScreen      | 全屏展示                                                                                                                                                                                                    | boolean                                     | -        |          |
| disableScroll   | 当点击 document 的时候，如果包含该节点则不会关闭弹层，<br/>如果是函数需要返回 ref，如果是字符串则是该 DOM 的 id，也可以直接传入 DOM 节点，或者以上值组成的数组<br/>是否禁用滚动，仅在 fullScreen 模式下生效 | boolean                                     | false    |          |
| children        | 子元素                                                                                                                                                                                                      | React.ReactNode                             | -        |          |
| onVisibleChange | 全屏模式下，loading弹层请求关闭时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_type_: 弹层关闭的来源<br/>_e_: DOM 事件                                                                               | (type: string, e: React.MouseEvent) => void | -        |          |
| safeNode        | 安全节点，仅在 fullScreen 时有效                                                                                                                                                                            | PopupProps['safeNode']                      | -        |          |

## 无障碍键盘操作指南

| 按键 | 说明                                                    |
| :--- | :------------------------------------------------------ |
| Esc  | 全屏模式下onVisibleChange接收的键盘事件，用于退出加载态 |


---


## menu

# zh-CN order=2

# 内连菜单展开模式

通过设置 openMode 为 `single`，可以让菜单同时只能展开一个内连子菜单，默认为可以同时展开多个。

# en-US order=2

# Expand mode of inline menu

You can make the inline menu expand only one submenu at the same time by setting openMode to 'single'. By default, you can expand more than one at a time.


---


## menu

# zh-CN order=0

# 基本

展示 Menu 的所有 UI 能力，例如菜单项、不可用菜单项、分组项、可展开项、链接项等。

# en-US order=0

# Basic

Demo the basic usage.


---


## menu

# zh-CN order=6

# 右键菜单

展示如何创建自定义的上下文菜单。

# en-US order=6

# Create context menu

Demo how to create the custom context menu.


---


## menu

# zh-CN order=7&debug=true

# 自定义菜单项选择

展示自定义组合菜单项可选的用法。

# en-US order=7&debug=true

# Customize menu item selection

Demo how to customize menu item selection.


---


## menu

# zh-CN order=4

# 自定义弹出内容

高级用法，可以通过 `Menu.PopupItem` 自定义菜单弹出内容。

# en-US order=4

# Customize pop up content

Demo how to customize pop up content.


---


## menu

# zh-CN order=3&debug=true

# hover 打开子菜单

可以设置 triggerType 为 `hover`，来 hover 打开子菜单，默认点击打开子菜单。

# en-US order=3&debug=true

# Open submenu by hover

You can set the triggerType to 'hover' to hover to open the submenu. By default, click to open the submenu.


---


## menu

# zh-CN order=1

# 超长折叠

在横向导航模式下，可通过设置 `hozInLine` 折叠超长内容。

# en-US order=1

# Horizontal menu bar

Demo the usage of the horizontal navigation menu bar.


---


## menu

# zh-CN order=2&debug=true

# 弹出菜单

展示弹出菜单的用法。

# en-US order=2&debug=true

# Pop up menu

Demo the usage of the popup up menu.


---


## menu

# zh-CN order=3

# 弹出菜单对齐方式

通过设置 popupAlign 为 `outside`，使弹出菜单和父级菜单对齐；或者设置为 `follow`，使弹出菜单和当前菜单项对齐。

# en-US order=3

# Alignment of the pop up menu

You can align the popup menu with the parent menu by setting popupAlign to 'outside'.


---


## menu

# zh-CN order=6

# 自定义渲染更多

复杂导航的例子，通过 `renderMore` 来展示更多

# en-US order=6

# Menu render more

Demo the usage of `renderMore`.


---


## menu

# zh-CN order=5&debug=true

# 选择与选中

展示菜单项选择用法。

# en-US order=5&debug=true

# Menu item selection

Demo the usage of menu item selection.


---


## menu

# zh-CN order=5

# 选择与选中

展示菜单项选择用法。

> -   单选带符号：一般用于 `Select` `CascaderSelect` 等单选模式下，需要数据返显，二次查看确认的组件中；
> -   单选不带符号：一般用于导航等，不需要数据返显的组件中；
> -   多选：必须要带符号

# en-US order=5

# Menu item selection

Demo the usage of menu item selection.


---


## menu

# Menu

-   category: Components
-   family: DataDisplay
-   chinese: 菜单
-   type: 展示

---

为页面和功能提供导航的菜单列表。

## 何时使用

导航菜单是一个网站的灵魂，用户依赖导航在各个页面中进行跳转。一般分为顶部导航和侧边导航，顶部导航提供全局性的类目和功能，侧边导航提供多级结构来收纳和排列网站架构。

## API

### Menu

| 参数                   | 说明                                                                                                                                                                          | 类型                                                                                                                   | 默认值     | 是否必填 |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------- | -------- |
| children               | 菜单项和子菜单                                                                                                                                                                | React.ReactNode                                                                                                        | -          |          |
| openKeys               | 当前打开的子菜单的 key 值（受控）                                                                                                                                             | string \| string[]                                                                                                     | -          |          |
| defaultOpenKeys        | 初始打开的子菜单的 key 值（非受控）                                                                                                                                           | string \| string[]                                                                                                     | []         |          |
| defaultOpenAll         | 初始展开所有的子菜单，只在 mode 设置为 'inline' 以及 openMode 设置为 'multiple' 下生效，优先级高于 defaultOpenKeys                                                            | boolean                                                                                                                | false      |          |
| onOpen                 | 打开或关闭子菜单触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_keys_: 打开的所有子菜单的 key 值<br/>_extra_: 当前被操作子菜单的信息                                     | (keys: string[], extra: { key: string; open: boolean }) => void                                                        | -          |          |
| mode                   | 子菜单打开的模式                                                                                                                                                              | Mode                                                                                                                   | 'inline'   |          |
| triggerType            | 子菜单打开的触发行为                                                                                                                                                          | 'click' \| 'hover'                                                                                                     | 'click'    |          |
| openMode               | 展开内连子菜单的模式，同时可以展开一个子菜单还是多个子菜单，该属性仅在 mode 为 inline 时生效                                                                                  | 'single' \| 'multiple'                                                                                                 | 'multiple' |          |
| inlineIndent           | 内连子菜单缩进距离                                                                                                                                                            | number                                                                                                                 | 20         |          |
| popupAutoWidth         | 是否自动让弹层的宽度和菜单项保持一致                                                                                                                                          | boolean                                                                                                                | false      |          |
| popupAlign             | 弹层的对齐方式                                                                                                                                                                | 'follow' \| 'outside'                                                                                                  | 'follow'   |          |
| popupProps             | 弹层自定义 props                                                                                                                                                              | PopupProps \| ((popupItemProps: PopupItemProps) => PopupProps)                                                         | -          |          |
| popupClassName         | 弹出子菜单自定义 className                                                                                                                                                    | string                                                                                                                 | -          |          |
| popupStyle             | 弹出子菜单自定义 style                                                                                                                                                        | React.CSSProperties                                                                                                    | -          |          |
| selectedKeys           | 当前选中菜单项的 key 值（受控）                                                                                                                                               | string \| string[]                                                                                                     | -          |          |
| defaultSelectedKeys    | 初始选中菜单项的 key 值（非受控）                                                                                                                                             | string \| string[]                                                                                                     | -          |          |
| onSelect               | 选中或取消选中菜单项触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_selectedKeys_: 选中的所有菜单项的值<br/>_item_: 选中或取消选中的菜单项<br/>_extra_: 选中时的额外参数 | (selectedKeys: string[], item: SelectableItem, extra: SelectExtra) => void                                             | -          |          |
| selectMode             | 选中模式，单选还是多选，默认无值，不可选                                                                                                                                      | 'single' \| 'multiple'                                                                                                 | -          |          |
| shallowSelect          | 是否只能选择第一层菜单项（不能选择子菜单中的菜单项）                                                                                                                          | boolean                                                                                                                | false      |          |
| hasSelectedIcon        | 是否显示选中图标，如果设置为 false 需配合配置平台设置选中时的背景色以示区分                                                                                                   | boolean                                                                                                                | true       |          |
| isSelectIconRight      | 是否将选中图标居右，仅当 hasSelectedIcon 为 true 时生效。                                                                                                                     | boolean                                                                                                                | false      |          |
| direction              | 菜单第一层展示方向                                                                                                                                                            | 'ver' \| 'hoz'                                                                                                         | 'ver'      |          |
| hozAlign               | 横向菜单条 item 和 footer 的对齐方向，在 direction 设置为 'hoz' 并且 header 存在时生效                                                                                        | 'left' \| 'right'                                                                                                      | 'left'     |          |
| header                 | 自定义菜单头部                                                                                                                                                                | React.ReactNode                                                                                                        | -          |          |
| footer                 | 自定义菜单尾部                                                                                                                                                                | React.ReactNode                                                                                                        | -          |          |
| footerWrapperClassName | 自定义菜单尾部容器的 className                                                                                                                                                | string                                                                                                                 | -          |          |
| autoFocus              | 是否自动获得焦点                                                                                                                                                              | boolean                                                                                                                | false      |          |
| focusedKey             | 当前获得焦点的子菜单或菜单项 key 值                                                                                                                                           | string                                                                                                                 | -          |          |
| focusable              | 是否可以获得焦点                                                                                                                                                              | boolean                                                                                                                | true       |          |
| onItemFocus            | 菜单项获得焦点时的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 菜单项的 key<br/>_item_: 菜单项组件实例<br/>_event_: 事件对象                                          | (<br/> key: string,<br/> item: MenuItem,<br/> event: React.MouseEvent \| React.KeyboardEvent<br/> ) => void            | -          |          |
| onItemClick            | 点击菜单项触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 点击的菜单项的 key 值<br/>_item_: 点击的菜单项对象<br/>_event_: 事件对象                                 | (<br/> key: string,<br/> item: MenuItem,<br/> event: React.MouseEvent \| React.KeyboardEvent<br/> ) => void            | -          |          |
| onItemKeyDown          | 菜单项触发键盘按下的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 菜单项的 key 值<br/>_item_: 菜单项对象<br/>_event_: 事件对象                                         | (<br/> key: string \| null \| undefined,<br/> item: MenuItem,<br/> event: React.KeyboardEvent<br/> ) => void           | -          |          |
| embeddable             | 是否开启嵌入式模式，开启后没有默认背景、外层 border、box-shadow                                                                                                               | boolean                                                                                                                | false      |          |
| icons                  | 自定义内部使用的图标                                                                                                                                                          | {<br/> select?: React.ReactNode;<br/> }                                                                                | -          |          |
| hozInLine              | 横向菜单模式下，是否维持在一行，即超出一行折叠成 SubMenu 显示                                                                                                                 | boolean                                                                                                                | -          |          |
| renderMore             | 自定义渲染超出一行的菜单项（hozInLine = true 时生效）<br/><br/>**签名**:<br/>**参数**:<br/>_items_: 被折叠的菜单项<br/>**返回值**:<br/>渲染内容                               | (<br/> items?: React.ReactElement[]<br/> ) => React.ReactElement\<{ className?: string; style?: React.CSSProperties }> | -          |          |
| inlineArrowDirection   | 子菜单展开箭头的方向                                                                                                                                                          | 'down' \| 'right'                                                                                                      | 'down'     |          |
| labelToggleChecked     | 标签是否可触发 checked 状态变化                                                                                                                                               | boolean                                                                                                                | true       |          |
| expandAnimation        | 展开菜单时使用动画                                                                                                                                                            | boolean                                                                                                                | true       |          |
| itemClassName          | 菜单项的类型                                                                                                                                                                  | string                                                                                                                 | -          |          |
| flatenContent          | 将菜单项 DOM 结构平铺在容器内                                                                                                                                                 | boolean                                                                                                                | -          |          |

### Menu.SubMenu

| 参数                    | 说明                                                     | 类型            | 默认值 | 是否必填 |
| ----------------------- | -------------------------------------------------------- | --------------- | ------ | -------- |
| label                   | 标签内容                                                 | React.ReactNode | -      |          |
| selectable              | 是否可选，该属性仅在设置 Menu 组件 selectMode 属性后生效 | boolean         | false  |          |
| mode                    | 子菜单打开方式，如果设置会覆盖 Menu 上的同名属性         | Mode            | -      |          |
| children                | 菜单项或下一级子菜单                                     | React.ReactNode | -      |          |
| level                   | 菜单层级                                                 | number          | -      |          |
| noIcon                  | 是否没有图标                                             | boolean         | false  |          |
| subMenuContentClassName | 子菜单内容节点的类名                                     | string          | -      |          |

### Menu.PopupItem

| 参数        | 说明                                                     | 类型                  | 默认值 | 是否必填 |
| ----------- | -------------------------------------------------------- | --------------------- | ------ | -------- |
| label       | 标签内容                                                 | React.ReactNode       | -      |          |
| children    | 自定义弹层内容                                           | React.ReactNode       | -      |          |
| hasSubMenu  | 是否拥有子菜单                                           | boolean               | -      |          |
| triggerType | 子菜单打开的触发方式，如果设置会覆盖 Menu 上的同名属性   | 'click' \| 'hover'    | -      |          |
| align       | 弹层的对齐方式                                           | 'follow' \| 'outside' | -      |          |
| selectable  | 是否可选，该属性仅在设置 Menu 组件 selectMode 属性后生效 | boolean               | false  |          |
| autoWidth   | 是否自动让弹层的宽度和菜单项保持一致                     | boolean               | -      |          |

### Menu.CheckboxItem

该子组件选中情况不受 defaultSelectedKeys/selectedKeys 控制，请自行控制选中逻辑

| 参数          | 说明                                                                                                        | 类型                                                                                                             | 默认值 | 是否必填 |
| ------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------ | -------- |
| checked       | 是否选中                                                                                                    | boolean                                                                                                          | false  |          |
| indeterminate | 是否半选中                                                                                                  | boolean                                                                                                          | false  |          |
| disabled      | 是否禁用                                                                                                    | boolean                                                                                                          | false  |          |
| onChange      | 选中或取消选中触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_checked_: 是否选中<br/>_event_: 事件对象 | (<br/> checked: boolean,<br/> event: React.MouseEvent \| React.KeyboardEvent \| React.ChangeEvent<br/> ) => void | -      |          |
| helper        | 帮助文本                                                                                                    | React.ReactNode                                                                                                  | -      |          |
| children      | 标签内容                                                                                                    | React.ReactNode                                                                                                  | -      |          |

### Menu.RadioItem

该子组件选中情况不受 defaultSelectedKeys/selectedKeys 控制，请自行控制选中逻辑

| 参数     | 说明                                                                                                        | 类型                                                                       | 默认值 | 是否必填 |
| -------- | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ------ | -------- |
| checked  | 是否选中                                                                                                    | boolean                                                                    | false  |          |
| disabled | 是否禁用                                                                                                    | boolean                                                                    | false  |          |
| onChange | 选中或取消选中触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_checked_: 是否选中<br/>_event_: 事件对象 | (checked: boolean, event: React.MouseEvent \| React.KeyboardEvent) => void | -      |          |
| helper   | 帮助文本                                                                                                    | React.ReactNode                                                            | -      |          |
| children | 标签内容                                                                                                    | React.ReactNode                                                            | -      |          |

### Menu.Group

| 参数     | 说明     | 类型                                   | 默认值 | 是否必填 |
| -------- | -------- | -------------------------------------- | ------ | -------- |
| label    | 标签内容 | React.ReactNode                        | -      |          |
| children | 菜单项   | React.ReactChild \| React.ReactChild[] | -      | 是       |

### Menu.Divider

分隔线

### SelectExtra

触发菜单选中状态变化时的额外信息

| 参数      | 说明                        | 类型              | 默认值 | 是否必填 |
| --------- | --------------------------- | ----------------- | ------ | -------- |
| key       | 被选中菜单的 key            | string            | -      | 是       |
| select    | 是否选中状态                | boolean           | -      | 是       |
| label     | 菜单的标签                  | React.ReactNode   | -      | 是       |
| keyPath   | 被操作菜单项的 key 全路径   | string[]          | -      | 是       |
| labelPath | 被操作菜单项的 label 全路径 | React.ReactNode[] | -      | 是       |

### Mode

子菜单打开的模式

```typescript
export type Mode = 'inline' | 'popup';
```

<!-- api-extra-start -->

### Menu.create(props)

创建上下文菜单。

-   props 参数可传入 Menu 所有支持的 props
-   props 额外支持 overlayProps，用来自定义 Menu 所在的弹层

<!-- api-extra-end -->

## 无障碍键盘操作指南

| 按键        | 说明                                                           |
| :---------- | :------------------------------------------------------------- |
| Up Arrow    | 导航到上一项                                                   |
| Down Arrow  | 导航到下一项                                                   |
| Right Arrow | 打开子菜单，导航到子菜单第一项；横向菜单条第一层，导航到右一项 |
| Left Arrow  | 关闭子菜单，导航到父级菜单；横向菜单条第一层，导航都左一项     |
| Enter       | 打开子菜单，导航到子菜单第一项                                 |
| Esc         | 关闭子菜单，导航到父级菜单                                     |
| SPACE       | 切换选中状态                                                   |


---


## menu-button

# zh-CN order=0

# 基本

最简单的用法。支持`Button`的 `shape`, `type`, `size`, `component`, `ghost` 等属性透传。

# en-US order=0

# Basic

Use MenuButton as Button.


---


## menu-button

# zh-CN order=2

# 复杂菜单

支持菜单组和菜单分割线，使用方法同 `Menu.Group`, `Menu.Item`, `Menu.Divider`。

# en-US order=2

# Menu

More complex case with custom menu.


---


## menu-button

# zh-CN order=3

# 多选菜单

通过 `selectMode` 控制菜单的选择模式。

# en-US order=3

# selectMode

Change select mode of menu by `selectMode`.


---


## menu-button

# zh-CN order=1

# 尺寸

可以通过 size 属性改变按钮大小。

# en-US order=1

# Size

Change component size by `size` attribute.


---


## menu-button

# MenuButton

-   category: Components
-   family: General
-   chinese: 菜单按钮
-   type: 基本

---

提供下拉菜单的按钮。

## 如何使用

1.  通过触发按钮打开弹层菜单。支持透传所有的 Button 属性。
2.  子组件 `Item`, `Group`, `Divider` 即 `Menu` 中对应的子组件，请参考 Menu 文档。

## API

### MenuButton

| 参数                | 说明                                                                                                                                                                 | 类型                                                            | 默认值  | 是否必填 |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- | ------- | -------- |
| label               | 按钮上的文本内容                                                                                                                                                     | React.ReactNode                                                 | -       |          |
| autoWidth           | 弹层是否与按钮宽度相同                                                                                                                                               | boolean                                                         | true    |          |
| popupTriggerType    | 弹层触发方式                                                                                                                                                         | 'click' \| 'hover'                                              | 'click' |          |
| popupContainer      | 弹层容器                                                                                                                                                             | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement) | -       |          |
| visible             | 弹层展开状态                                                                                                                                                         | boolean                                                         | -       |          |
| defaultVisible      | 弹层默认是否展开                                                                                                                                                     | boolean                                                         | -       |          |
| onVisibleChange     | 弹层在显示和隐藏触发的事件                                                                                                                                           | (visible: boolean, type: string) => void                        | -       |          |
| popupStyle          | 弹层自定义样式                                                                                                                                                       | React.CSSProperties                                             | -       |          |
| popupClassName      | 弹层自定义样式类                                                                                                                                                     | string                                                          | -       |          |
| popupProps          | 弹层属性透传                                                                                                                                                         | PopupProps                                                      | -       |          |
| followTrigger       | 菜单是否跟随滚动                                                                                                                                                     | boolean                                                         | -       |          |
| defaultSelectedKeys | 默认激活的菜单项（用法同 Menu 非受控）                                                                                                                               | Array\<string>                                                  | []      |          |
| selectedKeys        | 激活的菜单项（用法同 Menu 受控）                                                                                                                                     | string \| Array\<string>                                        | -       |          |
| selectMode          | 菜单的选择模式，同 Menu                                                                                                                                              | 'single' \| 'multiple'                                          | -       |          |
| onItemClick         | 点击菜单项后的回调，同 Menu<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 点击的菜单项的 key 值<br/>_item_: 点击的菜单项对象<br/>_event_: 事件对象                     | MenuProps['onItemClick']                                        | -       |          |
| onSelect            | 选择菜单后的回调，同 Menu<br/><br/>**签名**:<br/>**参数**:<br/>_selectedKeys_: 选中的所有菜单项的值<br/>_item_: 选中或取消选中的菜单项<br/>_extra_: 选中时的额外参数 | MenuProps['onSelect']                                           | -       |          |
| menuProps           | 菜单属性透传                                                                                                                                                         | MenuProps                                                       | -       |          |


---


## message

# zh-CN order=10&debug=true

# 无障碍支持

通过`Enter`键点击`button`时，自动聚焦到`Message`上读取信息。

# en-US order=10

# Accessibility

When you click `button` through the Enter key, it automatically focuses on `Message` to read the information.


---


## message

# zh-CN order=0

# 基本

简单的信息提示反馈。

# en-US order=0

# Basic Usage

Basic usage of Message.


---


## message

# zh-CN order=4

# 受控显示

通过`visible`设置受控显示或隐藏。

# en-US order=4

# Show and hide under controll

Control visibility of Message by `visibile`.


---


## message

# zh-CN order=8

# 自定义样式

使用 `style` 和 `className` 来定义样式。

# en-US order=8

# Custom Style

You can set message style by using `className` and `style`.


---


## message

# zh-CN order=3

# 可关闭提示

通过`closeable`设置用户手动关闭提示框。

# en-US order=3

# Closeable

You can control whether the message can be closed by adding the `closeable` property.


---


## message

# zh-CN order=2

# 提示尺寸与外观

通过`size`和`shape`调整信息提示的尺寸和外观。

# en-US order=2

# Size and Shape

You can control the size and shape of message by setting the `size` and `shape` property.


---


## message

# zh-CN order=5

# 弹窗用法

信息提示的弹窗用法，可以通过`Message.show`和`Message.hide`方法来显示或隐藏。

# en-US order=5

# Toast

You can use `Message.show` and `Message.hide` to show and hide toast conveniently.


---


## message

# zh-CN order=6

# 弹窗便捷用法

可以通过`Message.success`等静态方法来快速显示指定类型的信息弹窗。

# en-US order=6

# Quick way of toast

You can use static method such as `Message.success` to show the specified type toast.


---


## message

# zh-CN order=6

# 多实例弹窗

可以通过`Message.config` 开启多实例方式，后续 2.0 版本将默认使用多实例的方式。

# en-US order=6

# Quick way of toast

You can use static method `Message.config` to enable mutiple toast.


---


## message

# zh-CN order=1

# 常用提示类型

通过设置`type`调整信息类型，包括成功、警告、错误、通知、帮助、加载。

# en-US order=1

# Type

You can control the type of message by setting the `type` property.


---


## message

# zh-CN order=7&debug=true

# 更新消息内容

通过唯一的 `key` 来动态更新内容。

# en-US order=7

# Closeable

You can update message content by using unique `key`.


---


## message

# zh-CN order=9

# withContext

此功能1.21.6版本添加。

通过 `Message.withContext(({ contextMessage }) => {} )`方法，封装 使用到函数式调用弹窗 的组件（例如业务组件或者当前App等），可以将 被封装组件 代码所在上下文的context注入到`contextMessage`中。

相比较`Message.success()`获取到的是当前页面第一次被记录且未被卸载的context，`context Message.success()`获取到的是 链接示例中`< AfterFix /> `所在代码环境的context。

`contextMessage`上可被调用的方法有`success`、`error`、`notice`、`help`、`loading`、`show`、`hide`，注意`contextMessage`只有`Message`的函数式调用方法，它不能像 `<Message />` 一样被使用。

# en-US order=9

# withContext

Use `Message.withContext` to render Message imperatively. Avoid using `Message.[success|error|notice|help|loading|show|hide]`. `Message.withContext` helps you avoid "wrong fusion config" bug. For more details, check out the doc for `Dialog.withContext`.


---


## message

# Message

-   category: Components
-   family: Feedback
-   chinese: 信息提示
-   type: 展示

---

全局展示操作反馈信息。

## 何时使用

-   可提供成功、警告和错误等反馈信息。
-   顶部居中显示并自动消失，是一种不打断用户操作的轻量级提示方式。

## API

### Message

| 参数           | 说明                                                        | 类型                                                                 | 默认值      | 是否必填 |
| -------------- | ----------------------------------------------------------- | -------------------------------------------------------------------- | ----------- | -------- |
| type           | 反馈类型                                                    | 'success' \| 'warning' \| 'error' \| 'notice' \| 'help' \| 'loading' | 'success'   |          |
| shape          | 反馈外观                                                    | 'inline' \| 'addon' \| 'toast'                                       | 'inline'    |          |
| size           | 反馈大小                                                    | 'medium' \| 'large'                                                  | 'medium'    |          |
| title          | 标题                                                        | React.ReactNode                                                      | -           |          |
| children       | 内容，非函数式调用下使用                                    | React.ReactNode                                                      | -           |          |
| defaultVisible | 默认是否显示                                                | boolean                                                              | false       |          |
| visible        | 当前是否显示                                                | boolean                                                              | -           |          |
| iconType       | 显示的图标类型，会覆盖内部设置的IconType，传false不显示图标 | string \| false                                                      | -           |          |
| closeable      | 显示关闭按钮                                                | boolean                                                              | false       |          |
| onClose        | 关闭按钮的回调                                              | () => void                                                           | () =\> \{\} |          |
| afterClose     | 关闭之后调用的函数                                          | () => void                                                           | () =\> \{\} |          |
| animation      | 是否开启展开收起动画                                        | boolean                                                              | true        |          |

### Message.show

Message.show(props) 提供一个单例的调用方式，配置参数如下（继承 Overlay 的配置）：

```js
Message.show({
    type: 'error',
    title: '错误',
    content: '请联系相关人员反馈！',
    hasMask: true,
});
```

| 参数         | 说明                                      | 类型                                                                 | 默认值      | 是否必填 |
| ------------ | ----------------------------------------- | -------------------------------------------------------------------- | ----------- | -------- |
| type         | 反馈类型                                  | 'success' \| 'warning' \| 'error' \| 'notice' \| 'help' \| 'loading' | 'success'   |          |
| size         | 反馈大小                                  | 'medium' \| 'large'                                                  | 'medium'    |          |
| title        | 标题                                      | React.ReactNode                                                      | -           |          |
| content      | 内容，函数式调用下使用                    | React.ReactNode                                                      | -           |          |
| align        | 弹层对齐方式，详情见 Overlay align        | string \| boolean                                                    | 'tc tc'     |          |
| offset       | 弹层相对于参照元素定位的微调              | Array\<number>                                                       | [0, 0]      |          |
| hasMask      | 是否显示遮罩                              | boolean                                                              | false       |          |
| duration     | 显示持续时间，0表示一直存在，以毫秒为单位 | number                                                               | 3000        |          |
| closeable    | 显示关闭按钮                              | boolean                                                              | false       |          |
| onClose      | 关闭按钮的回调                            | () => void                                                           | () =\> \{\} |          |
| afterClose   | 关闭之后调用的函数                        | () => void                                                           | () =\> \{\} |          |
| animation    | 是否开启展开收起动画                      | boolean                                                              | true        |          |
| overlayProps | 透传到弹层组件的属性对象                  | OverlayProps                                                         | -           |          |

<!-- api-extra-start -->

### Message.hide

`Message.hide()` 提供关闭反馈弹层的快捷方法。

### Message.[success|error|notice|help|loading]

`Message.show({type: type, title: 'xxx'});` 的便捷调用方法。

示例：

```js
Message.success('反馈内容');

// 或者
Message.success({
    title: '反馈内容',
    duration: 1000,
});
```

### Message.withContext

1.21.6加入，建议通过这个HOC来获得命令式调起Message的API，而尽量不使用 `Message.[success|error|notice|help|loading|show|hide]`，能避免fusion config错误的bug，详细原因参考 `Dialog.withContext` 的文档。

### Message.config 配置多实例

`@alifd/next@1.24.0` 加入，配置后会采用多实例的方式

```js
Message.config({
    top: 100,
    duration: 2000,
    maxCount: 3,
});
```

| 参数     | 说明                           | 类型   | 默认值 |     |
| -------- | ------------------------------ | ------ | ------ | --- |
| duration | 默认自动关闭延时，单位毫秒     | Number | 3000   |     |
| top      | 消息距离顶部的位置             | Number | 8      |     |
| maxCount | 最多同时出现的个数, 默认不限制 | Number | -      |     |

```js
const instance = Message.success('this is a message');

instance.close(); // 可以用 close 直接关闭弹窗
```

<!-- api-extra-end -->

## 无障碍键盘操作指南

弹窗`Message`没有键盘操作，需要结合其他组件使用来聚焦提示，参考上文[#无障碍支持](#accessibility-container)。


---


## nav

# zh-CN order=2

# 只显示图标-宽度自适应

Nav 可设置 iconOnly 属性，只显示图标，以减少占用空间。通过设定 iconOnlyWidth 为 100%，可以实现 iconOnly 场景下 icon 自适应居中展示，需要注意的是这种情况下需要 Nav 外部容器有具体宽度。

# en-US order=2

# Only show icon - width adaptive

The Nav component can be configured with the iconOnly property to display only icons, minimizing occupied space‌12. By setting iconOnlyWidth to 100%, the icons will auto-center adaptively in iconOnly mode‌2. Note that this requires the external container of Nav to have a specific width‌.


---


## nav

# zh-CN order=0

# 顶部导航

水平的顶部导航菜单，四种样式模式可选。可以通过 `noIcon` 显示/隐藏下拉展开按钮

# en-US order=0

# Basic

The simplest way to use it.


---


## nav

# zh-CN order=1&debug=true

# 定制

Nav 提供了丰富的配置，可以进行个性化定制。

# en-US order=1

# Customize

Nav provides a lot of configurations that can be personalized.


---


## nav

# zh-CN order=6

# fixed模式

固定导航下的使用方式

# en-US order=6

# Fixed mode

How to use fixed navigation.


---


## nav

# zh-CN order=3

# 分组

建议只在垂直布局中使用。

# en-US order=3

# Group

Nav could set the iconOnly property to reduce the footprint.


---


## nav

# zh-CN order=2&debug=true

# 只显示图标

Nav 可设置 iconOnly 属性，只显示图标，以减少占用空间。

# en-US order=2

# Only show icon

Nav could set the iconOnly property to reduce the footprint.


---


## nav

# zh-CN order=4

# 只展开当前父级菜单

通过 openMode 一键开启。在内嵌模式下，保证最多只有一个同级菜单被展开，收起其他展开的所有菜单，保持菜单聚焦简洁。

# en-US order=4

# Open mode

When yout set mode of Nav to inline, openMode could controls the number of expanded sub navigation at same time.


---


## nav

# zh-CN order=5

# 弹出型子菜单的顶部对齐

通过 popupAlign 一键设置。用于菜单深度较浅，但子菜单内容较多的场景。

# en-US order=5

# Popup alignment

When you set mode of Nav to popup, popAlign could controls the alignment of the pop sub navigation.


---


## nav

# zh-CN order=1

# 左侧内嵌导航

垂直菜单，子菜单内嵌在菜单区域，四种样式模式可选。

# en-US order=2

# Only show icon

Vertical navigation, there are four styles to be selected.


---


## nav

# zh-CN order=2

# 缩起内嵌菜单

内嵌菜单可以被缩起/展开。
Nav背景与环境背景不同? 开启embeddable试试，完美嵌入环境:

-   当开启 `embeddable` 模式后，Nav组件适合被嵌入到有背景色的页面部分，当作导航。可以根据背景色色系选择不同的type；
-   当未开启 `embeddable` 模式时，Nav组件将带有背景色、border、阴影等，可以单独使用。

# en-US order=2

# Only show icon

Nav could set the iconOnly property to reduce the footprint.


---


## nav

# Nav

-   category: Components
-   family: Navigation
-   chinese: 导航
-   type: 导航
-   cols: 1

---

## 何时使用

分为顶部导航和侧边导航，顶部导航提供全局性的类目和功能，侧边导航提供多级结构来收纳和排列网站架构。

## 如何使用

Nav 继承自 Menu，除特殊说明外，可使用 Menu 的 API。

## API

### Nav

| 参数                | 说明                                                                                                                                                         | 类型                                                                       | 默认值     | 是否必填 | 支持版本 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------- | ---------- | -------- | -------- |
| children            | 导航项和子导航                                                                                                                                               | React.ReactNode                                                            | -          |          | -        |
| defaultOpenAll      | 初始展开所有的子导航                                                                                                                                         | boolean                                                                    | false      |          | -        |
| mode                | 子导航打开的模式                                                                                                                                             | 'inline' \| 'popup'                                                        | 'inline'   |          | -        |
| triggerType         | 子导航打开的触发方式                                                                                                                                         | 'click' \| 'hover'                                                         | 'click'    |          | -        |
| openMode            | 内联子导航的展开模式，同时可以展开一个同级子导航还是多个同级子导航                                                                                           | 'single' \| 'multiple'                                                     | 'multiple' |          | -        |
| inlineIndent        | 内联子导航缩进距离                                                                                                                                           | number                                                                     | 20         |          | -        |
| popupAlign          | 弹出子导航的对齐方式                                                                                                                                         | 'follow' \| 'outside'                                                      | 'follow'   |          | -        |
| popupClassName      | 弹出子导航的自定义类名                                                                                                                                       | string                                                                     | -          |          | -        |
| selectedKeys        | 当前选中导航项的 key 值                                                                                                                                      | string \| Array\<string>                                                   | -          |          | -        |
| defaultSelectedKeys | 初始选中导航项的 key 值                                                                                                                                      | string \| Array\<string>                                                   | []         |          | -        |
| onSelect            | 选中或取消选中导航项触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_selectedKeys_: 选中的导航项的 key 值<br/>_item_: 选中的导航项<br/>_extra_: 扩展参数 | (selectedKeys: string[], item: SelectableItem, extra: SelectExtra) => void | -          |          | -        |
| direction           | 导航布局                                                                                                                                                     | 'hoz' \| 'ver'                                                             | 'ver'      |          | -        |
| hozAlign            | 横向导航条 items 和 footer 的对齐方向                                                                                                                        | 'left' \| 'right'                                                          | 'left'     |          | -        |
| header              | 自定义导航头部                                                                                                                                               | React.ReactNode                                                            | -          |          | -        |
| footer              | 自定义导航尾部                                                                                                                                               | React.ReactNode                                                            | -          |          | -        |
| embeddable          | 是否开启嵌入式模式                                                                                                                                           | boolean                                                                    | false      |          | 1.18     |
| type                | 导航类型                                                                                                                                                     | 'normal' \| 'primary' \| 'secondary' \| 'line'                             | 'normal'   |          | -        |
| activeDirection     | 设置组件选中状态的 active 边方向                                                                                                                             | null \| 'top' \| 'bottom' \| 'left' \| 'right'                             | -          |          | -        |
| iconOnly            | 是否只显示图标                                                                                                                                               | boolean                                                                    | -          |          | -        |
| iconTextOnly        | iconOnly 模式下是否展示文字                                                                                                                                  | boolean                                                                    | -          |          | -        |
| iconOnlyWidth       | iconOnly 模式下的宽度                                                                                                                                        | number \| string                                                           | -          |          | -        |
| hasArrow            | 是否显示右侧的箭头                                                                                                                                           | boolean                                                                    | true       |          | -        |
| hasTooltip          | 是否有 ToolTips                                                                                                                                              | boolean                                                                    | false      |          | -        |

### Nav.Group

| 参数     | 说明           | 类型                                   | 默认值 | 是否必填 |
| -------- | -------------- | -------------------------------------- | ------ | -------- |
| label    | 标签内容       | React.ReactNode                        | -      |          |
| children | 导航项和子导航 | React.ReactChild \| React.ReactChild[] | -      | 是       |

### Nav.Item

| 参数     | 说明       | 类型                      | 默认值 | 是否必填 |
| -------- | ---------- | ------------------------- | ------ | -------- |
| icon     | 自定义图标 | string \| React.ReactNode | -      |          |
| children | 导航内容   | React.ReactNode           | -      |          |

### Nav.PopupItem

| 参数     | 说明       | 类型                      | 默认值 | 是否必填 |
| -------- | ---------- | ------------------------- | ------ | -------- |
| label    | 标签内容   | React.ReactNode           | -      |          |
| children | 弹出内容   | React.ReactNode           | -      |          |
| icon     | 自定义图标 | string \| React.ReactNode | -      |          |

### Nav.SubNav

| 参数       | 说明                                        | 类型                      | 默认值 | 是否必填 |
| ---------- | ------------------------------------------- | ------------------------- | ------ | -------- |
| icon       | 自定义图标                                  | string \| React.ReactNode | -      |          |
| label      | 标签内容                                    | React.ReactNode           | -      |          |
| selectable | 是否可选                                    | boolean                   | false  |          |
| children   | 导航项和子导航                              | React.ReactNode           | -      |          |
| noIcon     | 是否需要提示当前项可展开的 icon，默认是有的 | boolean                   | -      |          |

## 无障碍键盘操作指南

| 按键        | 说明                                                           |
| :---------- | :------------------------------------------------------------- |
| Up Arrow    | 导航到上一项                                                   |
| Down Arrow  | 导航到下一项                                                   |
| Right Arrow | 打开子菜单，导航到子菜单第一项；横向菜单条第一层，导航到右一项 |
| Left Arrow  | 关闭子菜单，导航到父级菜单；横向菜单条第一层，导航到左一项     |
| Enter       | 打开子菜单，导航到子菜单第一项                                 |
| Esc         | 关闭子菜单，导航到父级菜单                                     |

## FAQ

### 菜单的数据是移步获取的，当我拿到数据之后，发现设置的 `defaultOpenKeys` 不生效，有什么解决办法？

原因：defaultXXX系列API遵循React的设计规范，仅在组件第一次渲染的时候生效，所以`defaultOpenKeys`仅仅对Menu在didMount阶段拿到的Children生效，异步获取的信息不在这个阶段内，所以不生效。

解决方法：假设菜单信息是异步获取后塞到 menuData 变量中的，可以设置 `{menuData && <Menu />}`。


---


## notification

# zh-CN order=0

# 基本

最简单的用法, 4.5s 后关闭

# en-US order=0

# Basic

Simplest use, closed after 4.5


---


## notification

# zh-CN order=1

# 自动关闭延时

自定义关闭的延迟，默认 `4.5s`, 为 `0` 时则一直存在

# en-US order=1

# Duration

`Duration` can be used to specify how long the notification stays open. After the duration time elapses, the notification closes automatically. If not specified, default value is 4.5 seconds. If you set the value to 0, the notification box will never close automatically.


---


## notification

# zh-CN order=3

# 自定义图标

可以设置使用的图标

# en-US order=3

# Custom Icon

Change Icon


---


## notification

# zh-CN order=4

# 位置

可以设置通知从右上角、右下角、左下角、左上角弹出。

# en-US order=4

# Position

Can setting `tl`, `tr`, `bl`, `br`


---


## notification

# zh-CN order=6

# 自定义样式

使用 `style` 和 `className` 来定义样式。

# en-US order=6

# Custom Style

use `style` or `className` to custom style;


---


## notification

# zh-CN order=2

# 常用类型的通知框

`success`, `warning`, `error`, `notice`, `help` 类型的通知框。

# en-US order=2

# Level Notification

More Noticfiction types.


---


## notification

# zh-CN order=5

# 更新通知内容

可以通过唯一的 `key` 来更新内容。

# en-US order=5

# Update Content

Update content with unique key.


---


## notification

# Notification

-   category: Components
-   family: Feedback
-   chinese: 通知
-   type: 展示
-   version: 1.18

---

全局展示通知提醒信息。

## 何时使用

在系统四个角显示通知提醒信息。经常用于以下情况：

-   较为复杂的通知内容。
-   带有交互的通知，给出用户下一步的行动点。
-   系统主动推送。

## API

### Notification

| 参数    | 说明 | 类型                                               | 默认值 | 是否必填 |
| ------- | ---- | -------------------------------------------------- | ------ | -------- |
| config  | -    | (config: NotificationConfig) => NotificationConfig | -      | 是       |
| open    | -    | (options: NotificationOptions) => string           | -      | 是       |
| close   | -    | (key: string) => void                              | -      | 是       |
| destroy | -    | () => void                                         | -      | 是       |
| success | -    | (options: NotificationOptions) => string           | -      | 是       |
| error   | -    | (options: NotificationOptions) => string           | -      | 是       |
| warning | -    | (options: NotificationOptions) => string           | -      | 是       |
| notice  | -    | (options: NotificationOptions) => string           | -      | 是       |
| help    | -    | (options: NotificationOptions) => string           | -      | 是       |

### Notification.Config

| 参数         | 说明                               | 类型                                                     | 默认值                | 是否必填 |
| ------------ | ---------------------------------- | -------------------------------------------------------- | --------------------- | -------- |
| offset       | 对齐之后的偏移 [x, y]              | [number, number]                                         | [30, 30]              |          |
| maxCount     | 最多同时出现的个数, 默认不限制     | number                                                   | -                     |          |
| size         | 使用 `Message` 组件的              | 'large' \| 'medium'                                      | large                 |          |
| duration     | 默认自动关闭延时，单位毫秒         | number                                                   | 4500                  |          |
| getContainer | 配置渲染节点的输出位置             | () => HTMLElement                                        | `() => document.body` |          |
| placement    | 弹出位置，可选 `tl` `tr` `bl` `br` | 'topRight' \| 'topLeft' \| 'bottomLeft' \| 'bottomRight' | topRight              |          |

### NotificationOptions

| 参数      | 说明                                                                                                                                                | 类型              | 默认值      | 是否必填   |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- | ----------- | ---------- | ------ | ------------------------------------------------------- | --------- | --- |
| key       | 当前通知唯一标志, 默认会自动生成                                                                                                                    | string            | -           |            |
| type      | 通知类型，`Notification.open`可选参数，可选值：`success`\\                                                                                          | `error`\\         | `warning`\\ | `notice`\\ | `help` | 'success' \| 'error' \| 'warning' \| 'notice' \| 'help' | `success` |     |
| title     | 通知提醒标题                                                                                                                                        | ReactNode         | -           |            |
| content   | 通知提醒内容                                                                                                                                        | ReactNode         | -           |            |
| icon      | 自定义图标                                                                                                                                          | string            | -           |            |
| duration  | 默认 4.5 秒后自动关闭，配置为 0 则不自动关闭（单位毫秒）                                                                                            | number            | 4500        |            |
| style     | 自定义内联样式 [详见](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/e434515761b36830c3e58a970abf5186f005adac/types/react/index.d.ts#L794) | CSSProperties     | -           |            |
| className | 自定义 CSS class                                                                                                                                    | string            | -           |            |
| onClose   | 点击默认关闭按钮时触发的回调函数                                                                                                                    | () => void        | -           |            |
| onClick   | 点击通知时触发的回调函数                                                                                                                            | MouseEventHandler | -           |            |


---


## number-picker

# zh-CN order=11

# 无障碍支持

组件内置了部分支持无障碍, 但是额外需要开发者手动设置才能完整支持无障碍: 设置upBtnprops以及downBtnprops，使得读屏软件可以正确表达按键的具体功能。设置`aria-live`目的是`NumberPicker`组件值发生改变时，读屏软件会进行读取。

# en-US order=11

# Accessibility

The component is partially built to support accessibility, but requires additional developer manual Settings to fully support accessibility: upBtnprops and downBtnprops are set up to enable the screen reader to correctly express the specific functions of the buttons. set `aria-live` purpose is `NumberPicker` component value change, screen reader will be read.


---


## number-picker

# zh-CN order=0

# 基本用法

onChange 第二个参数 e.type 可以获取事件类型。

如果是点击`+` `-` 触发，可以通过 `e.triggerType` 获取

# en-US order=0

# Basic usage

you can get event type from onChange function second param `e.type`。

if events are triggered by '+' button or '-' button, you can get event type from onChange function third param `e.triggerType`.


---


## number-picker

# zh-CN order=8

# 大数与高精度小数

通过 `stringMode` 开启 大数 与 高精度小数 支持，输入输出都变为 `String` 类型。

# en-US order=8

# support big number

get big number support via `stringMode`


---


## number-picker

# zh-CN order=6

# 不可用

不可用的 number picker。

# en-US order=6

# Disable

disable number picker。


---


## number-picker

# zh-CN order=1

# 不可直接输入

用户不可直接输入编辑数据

# en-US order=1

# Forbid Input

Forbid directly inputting data, only allow changing data by clicking button


---


## number-picker

# zh-CN order=7

# 格式化

# en-US order=7

# Formatting


---


## number-picker

# zh-CN order=2

# 最大最小值

min max 来限制value的最大最小值。

当数据自动订正会触发 onCorrect

# en-US order=2

# max-min

Use the param `min` to limit minimum value,
Use the param `max` to limit maximum value,

That the value exceeds `min` or `max` will trigger onCorrect.


---


## number-picker

# zh-CN order=10

# 移动端

device=phone/tablet 下会强制设置 type=inline

# en-US order=10

# Basic Usage

force set type=inline while device=phone


---


## number-picker

# zh-CN order=4

# 精度

通过 precision 控制小数点位数

# en-US order=4

# precision

Use precision to Control the number of decimal places.


---


## number-picker

# zh-CN order=5

# 大小

# en-US order=5

# size


---


## number-picker

# zh-CN order=3

# 步长

通过step控制每次加减步长

# en-US order=3

# step

Use step to control the number change every click.


---


## number-picker

# zh-CN order=9

# 按钮控制

控制按钮一致显示、隐藏

# en-US order=9

# trigger controls

control button trigger show without hover or hide


---


## number-picker

# NumberPicker

-   category: Components
-   family: DataEntry
-   chinese: 数字输入框
-   type: 表单

---

数字选择器。

## 何时使用

数字选择器，并对输入的数据做正确性检查、自动订正。

## 如何使用

1.  自动订正可能会导致 onChange 返回值和你输入的数据不一样。

2.  其中有些中间输入状态无法触发 onChange，主要考虑到自动订正可能永远无法到达想要的值了。例如：

    -   `0`=>`0.`=>`0.0`=>`0.01` 中间两步不会触发 onChange，因为如果订正会一直停留在 0 导致永远无法到达想要的值
    -   min=10 的情况下，输入 `1`=>`12` 第一步 `1` 不会触发 onChange 也不会订正数据，因为数字是一个一个输入的

3.  如果输入时没触发 onChange，会在 onBlur 检测数据正确性并触发 onChange

4.  在 `1.24` 版本加入大数支持，通过 `stringMode` 开启大数或高精度小数支持，输入输出都变为 `String` 类型，具体参考[大数与高精度小数](#bignumber-container)

5.  如果需要输入小数，需设置 `precision` 小数点位数

## API

### NumberPicker

| 参数              | 说明                                                                                                                                               | 类型                                                                                                                                                                                                                                                                                                                                                                            | 默认值    | 是否必填 | 支持版本 |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | -------- | -------- |
| size              | 大小                                                                                                                                               | 'large' \| 'medium' \| 'small'                                                                                                                                                                                                                                                                                                                                                  | 'medium'  |          | -        |
| type              | 设置类型(当 device 为 phone 时，NumberPicker 的类型强制为 normal，不可通过 type 修改)                                                              | 'normal' \| 'inline'                                                                                                                                                                                                                                                                                                                                                            | 'normal'  |          | -        |
| value             | 当前值                                                                                                                                             | number \| string                                                                                                                                                                                                                                                                                                                                                                | -         |          | -        |
| defaultValue      | 默认值                                                                                                                                             | number \| string                                                                                                                                                                                                                                                                                                                                                                | -         |          | -        |
| disabled          | 是否禁用                                                                                                                                           | boolean                                                                                                                                                                                                                                                                                                                                                                         | -         |          | -        |
| step              | 步长                                                                                                                                               | number \| string                                                                                                                                                                                                                                                                                                                                                                | 1         |          | -        |
| precision         | 保留小数点后位数                                                                                                                                   | number                                                                                                                                                                                                                                                                                                                                                                          | 0         |          | -        |
| editable          | 用户是否可以输入                                                                                                                                   | boolean                                                                                                                                                                                                                                                                                                                                                                         | true      |          | -        |
| autoFocus         | 自动焦点                                                                                                                                           | boolean                                                                                                                                                                                                                                                                                                                                                                         | -         |          | -        |
| onChange          | 数值被改变的事件<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 新的数值。<br/>_e_: DOM 事件对象。                                                  | (<br/> value: number \| string \| undefined,<br/> e: (<br/> \| React.ChangeEvent\<HTMLInputElement><br/> \| React.CompositionEvent\<HTMLInputElement><br/> \| React.KeyboardEvent\<HTMLInputElement><br/> \| React.FocusEvent\<HTMLInputElement><br/> \| React.KeyboardEvent\<HTMLInputElement><br/> ) & {<br/> triggerType: 'up' \| 'down' \| undefined;<br/> }<br/> ) => void | func.noop |          | -        |
| onKeyDown         | 键盘按下<br/><br/>**签名**:<br/>**参数**:<br/>_e_: DOM 事件对象。                                                                                  | InputProps['onKeyDown']                                                                                                                                                                                                                                                                                                                                                         | func.noop |          | -        |
| onFocus           | 焦点获得<br/><br/>**签名**:<br/>**参数**:<br/>_e_: DOM 事件对象。                                                                                  | InputProps['onFocus']                                                                                                                                                                                                                                                                                                                                                           | -         |          | -        |
| onBlur            | 焦点失去<br/><br/>**签名**:<br/>**参数**:<br/>_e_: DOM 事件对象。                                                                                  | InputProps['onBlur']                                                                                                                                                                                                                                                                                                                                                            | func.noop |          | -        |
| onCorrect         | 数值订正后的回调<br/><br/>**签名**:<br/>**参数**:<br/>_obj_: 包含 currentValue 和 oldValue 的对象。                                                | (obj: { currentValue: number \| string; oldValue: number \| string }) => void                                                                                                                                                                                                                                                                                                   | func.noop |          | -        |
| max               | 最大值                                                                                                                                             | number \| string                                                                                                                                                                                                                                                                                                                                                                | -         |          | -        |
| min               | 最小值                                                                                                                                             | number \| string                                                                                                                                                                                                                                                                                                                                                                | -         |          | -        |
| format            | 格式化当前值<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 当前的数值。<br/>**返回值**:<br/>格式化后的值，可以是字符串或数字。                     | (value: string \| number) => string \| number                                                                                                                                                                                                                                                                                                                                   | -         |          | -        |
| hasTrigger        | 是否展示点击按钮                                                                                                                                   | boolean                                                                                                                                                                                                                                                                                                                                                                         | true      |          | -        |
| alwaysShowTrigger | 是否一直显示点击按钮(无须hover)                                                                                                                    | boolean                                                                                                                                                                                                                                                                                                                                                                         | false     |          | -        |
| label             | 内联 左侧label                                                                                                                                     | React.ReactNode                                                                                                                                                                                                                                                                                                                                                                 | -         |          | -        |
| innerAfter        | 内联 右侧附加内容                                                                                                                                  | React.ReactNode                                                                                                                                                                                                                                                                                                                                                                 | -         |          | -        |
| upBtnProps        | 增加按钮的props                                                                                                                                    | ButtonProps                                                                                                                                                                                                                                                                                                                                                                     | -         |          | -        |
| downBtnProps      | 减少按钮的props                                                                                                                                    | ButtonProps                                                                                                                                                                                                                                                                                                                                                                     | -         |          | -        |
| isPreview         | 是否为预览态                                                                                                                                       | boolean                                                                                                                                                                                                                                                                                                                                                                         | -         |          | -        |
| renderPreview     | 预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 当前值。<br/>_props_: 传入的组件参数。<br/>**返回值**:<br/>Element 渲染内容。 | (value: number \| string, props: NumberPickerProps) => React.ReactNode                                                                                                                                                                                                                                                                                                          | -         |          | -        |
| stringMode        | 开启大数支持，输入输出均为string类型                                                                                                               | boolean                                                                                                                                                                                                                                                                                                                                                                         | false     |          | 1.24     |
| state             | 状态                                                                                                                                               | 'error' \| 'success'                                                                                                                                                                                                                                                                                                                                                            | -         |          | -        |

## 无障碍键盘操作指南

| 按键       | 说明     |
| :--------- | :------- |
| Up Arrow   | 数字增加 |
| Down Arrow | 数字减小 |


---


## overlay

# zh-CN order=6

# 对齐

通过 `align` 可以自定义对齐方式。

# en-US order=6

# Align

Use align prop to set align type


---


## overlay

# zh-CN order=1&debug=true

# 遮罩层

带有遮罩的弹层。

# en-US order=1

# Mask

The overlay with mask.


---


## overlay

# zh-CN order=0

# 基本

弹出一个弹层。

# en-US order=0

# Basic

Pop up a overlay.


---


## overlay

# zh-CN order=4

# 受控显示隐藏

展示了 `Popup` 受控显示隐藏的用法。

# en-US order=4

# Popup under control

Demos `Popup` under control usage.


---


## overlay

# zh-CN order=5

# 弹层嵌套

有弹层嵌套需求时，请使用 container 属性将第二个弹层渲染到第一个弹层内部。

# en-US order=5

# Nested overlay

When there is a overlay nesting requirement, use the container property to render the second overlay inside the first overlay.


---


## overlay

# zh-CN order=2

# Popup弹层

`Popup` 是对 `Overlay` 的封装，它接收某个节点作为触发节点，弹出一个浮层，这个浮层默认情况下使用这个节点作为定位的参照对象。

# en-US order=2

# Popup

Use popup to pop up a overlay.


---


## overlay

# zh-CN order=7

# 弹层自动跟随滚动

如果弹层显示隐藏的触发元素所在容器有滚动条，弹窗会自动更新自己的位置跟随滚动。但是实时更新会消耗较大的计算，可以通过更好挂载容器到父节点获得更好性能

# en-US order=7

# Overlay follows the container scroll

The overlay defaults to absolute positioning with reference to document.body. If the overlay trigger element's container (usually the parent node) has a scrollbar, then when the container is scrolled, the trigger element can be scroll autoly


---


## overlay

# zh-CN order=8&debug=true

# 弹层跟随问题

弹窗跟随测试demo

# en-US order=7

# Overlay follows the container scroll

The overlay defaults to absolute positioning with reference to document.body. If the overlay trigger element's container (usually the parent node) has a scrollbar, then when the container is scrolled, the trigger element can be scroll autoly


---


## overlay

# zh-CN order=3

# 动效

通过 `animation` 属性设置动效

# en-US order=3

# Popup

Use `animation` set motion.


---


## overlay

# zh-CN order=3

# 触发方式

通过 `triggerType` 属性设置触发方式。

# en-US order=3

# Popup

Use `triggerType` prop.


---


## overlay

# Overlay

-   category: Utility
-   family: Util
-   chinese: 弹层

---

用于生成弹层的工具类集合。

## 如何使用

Overlay 提供了一系列组件用于创建弹层。其中包含：

### `v2` 版本更新指示

1.25 版本增加 v2 支持开启新版本弹，功能如下：

功能变化：

-   弹窗位置计算的算法优化：一次即可完成位置计算，不会出现死循环、闪烁等情况。（上一个版本的弹窗打开可能会触发 n 次计算）
-   自动位置调整：根据空间的大小自动调整位置
-   彻底解决在滚动容器中 trigger 和 弹窗会分离的问题，新版本会自动调整位置。使用者不再需要去研究怎么用 container 修改弹窗挂载位置
-   彻底解决多层弹窗嵌套，点击子弹窗可能导致父弹窗消失的问题。

API变化：

### Overlay

Overlay 可以在页面中弹出一个浮层，封装了定位，动画及其他一些可用性的功能。Overlay 被设计为无状态的组件，其本身并不控制自己显示和隐藏的状态。

**注意:** 类似 canCloseby\* 的配置也需要配合 onRequestClose 才能关闭弹层。

#### 安全节点

Overlay 提供了点击弹层外文档中节点隐藏该弹层的功能，如果想让某个节点点击后不隐藏弹层（如：触发弹层打开的节点），请将该节点传入 safeNode 属性。

#### 定位

1.  align 的值可以是由空格隔开的字符串，如 `tl bl`，其中 `tl` 代表目标元素的左上方，`bl` 代表基准元素的左下方，所以 `tl bl` 的意思是目标元素的左上方对齐基准元素左下方。其中定位的可选值有 `tl`, `tc`, `tr`, `cl`, `cc`, `cr`, `bl`, `bc`, `br`。`t` 为 `top` 的缩写，`b` 为 `bottom` 的缩写，`c` 为 `center` 的缩写，`l` 为 `left` 的缩写，`r` 为 `right` 的缩写.

2.  align 支持的 Boolean 值仅为 false，在设置为 false 时，不使用 JS 定位，这样你可以根据你的需要传入 style 或者 className 进行 CSS 定位。

3.  rtl情况下会自动翻转 r(right)与 l(left),

### Popup

Popup 是对 Overlay 的封装，它接收某个节点作为触发节点，弹出一个浮层，这个浮层默认情况下使用这个节点作为定位的参照对象。

## API

### Overlay

| 参数                   | 说明                                                                                                                                                                | 类型                                                           | 默认值                                       | 是否必填 | 支持版本 |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------- | -------- | -------- |
| children               | 弹层内容                                                                                                                                                            | React.ReactElement & { ref?: React.RefCallback\<HTMLElement> } | -                                            |          | -        |
| visible                | 是否显示弹层                                                                                                                                                        | boolean                                                        | false                                        |          | -        |
| onRequestClose         | 弹层请求关闭时触发事件的回调函数，v2 版本第一个参数是 event                                                                                                         | (type: string, e: Event \| React.MouseEvent\<Element>) => void | -                                            |          | -        |
| target                 | 弹层定位的参照元素                                                                                                                                                  | PropTarget                                                     | Position.VIEWPORT                            |          | -        |
| align                  | 弹层相对于参照元素的定位，详见开发指南的 [定位部分](#定位)                                                                                                          | string \| boolean                                              | 'tl bl'                                      |          | -        |
| offset                 | 弹层相对于 trigger 的定位的微调，接收数组 [hoz, ver], 表示弹层在 left / top 上的增量 e.g. [100, 100] 表示往右 (RTL 模式下是往左) 、下分布偏移 100px                 | Array\<number>                                                 | [0, 0]                                       |          | -        |
| container              | 渲染组件的容器，如果是函数需要返回 ref，如果是字符串则是该 DOM 的 id，也可以直接传入 DOM 节点                                                                       | PropTarget                                                     | -                                            |          | -        |
| hasMask                | 是否显示遮罩                                                                                                                                                        | boolean                                                        | false                                        |          | -        |
| canCloseByEsc          | 是否支持 esc 按键关闭弹层                                                                                                                                           | boolean                                                        | true                                         |          | -        |
| canCloseByOutSideClick | 点击弹层外的区域是否关闭弹层，不显示遮罩时生效                                                                                                                      | boolean                                                        | true                                         |          | -        |
| canCloseByMask         | 点击遮罩区域是否关闭弹层，显示遮罩时生效                                                                                                                            | boolean                                                        | true                                         |          | -        |
| beforeOpen             | 弹层打开前触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| onOpen                 | 弹层打开时触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| afterOpen              | 弹层打开后触发事件的回调函数，如果有动画，则在动画结束后触发                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| beforeClose            | 弹层关闭前触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| onClose                | 弹层关闭时触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| afterClose             | 弹层关闭后触发事件的回调函数，如果有动画，则在动画结束后触发                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| beforePosition         | 弹层定位完成前触发的事件                                                                                                                                            | () => void                                                     | -                                            |          | -        |
| onPosition             | 弹层定位完成时触发的事件                                                                                                                                            | (config: object, node?: object) => void                        | -                                            |          | -        |
| shouldUpdatePosition   | 是否在每次弹层重新渲染后强制更新定位信息，一般用于弹层内容区域大小发生变化时，仍需保持原来的定位方式                                                                | boolean                                                        | false                                        |          | -        |
| autoFocus              | 弹层打开时是否让其中的元素自动获取焦点                                                                                                                              | boolean                                                        | false                                        |          | -        |
| needAdjust             | 当弹层由于页面滚动等情况不在可视区域时，是否自动调整定位以出现在可视区域                                                                                            | boolean                                                        | true                                         |          | -        |
| disableScroll          | 是否禁用页面滚动                                                                                                                                                    | boolean                                                        | false                                        |          | -        |
| cache                  | 隐藏时是否保留子节点                                                                                                                                                | boolean                                                        | false                                        |          | -        |
| safeNode               | 安全节点，当点击 document 的时候，如果包含该节点则不会关闭弹层，如果是函数需要返回 ref，如果是字符串则是该 DOM 的 id，也可以直接传入 DOM 节点，或者以上值组成的数组 | React.ReactNode                                                | -                                            |          | -        |
| wrapperClassName       | 弹层的根节点的样式类                                                                                                                                                | string                                                         | -                                            |          | -        |
| wrapperStyle           | 弹层的根节点的内联样式                                                                                                                                              | React.CSSProperties                                            | -                                            |          | -        |
| animation              | 配置动画的播放方式，支持 \{ in: 'enter-class', out: 'leave-class' \} 的对象参数，如果设置为 false，则不播放动画。请参考 Animate 组件的文档获取可用的动画名          | string \| boolean \| AnimationObjectType \| undefined          | \{ in: 'expandInDown', out: 'expandOutUp' \} |          | -        |
| v2                     | 开启 v2 版本                                                                                                                                                        | false \| undefined                                             | false                                        |          | 1.25     |
| points                 | [v2] align 的数组形式，不能和 align 同时使用                                                                                                                        | Array\<string>                                                 | -                                            |          | 1.25     |
| useCapture             | 是否在捕获阶段监听，适配 react 17 事件模型变更                                                                                                                      | boolean                                                        | -                                            |          | 1.25     |

### Overlay V2

| 参数                   | 说明                                                                                                                                                                | 类型                                                           | 默认值                                       | 是否必填 | 支持版本 |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------- | -------- | -------- |
| children               | 弹层内容                                                                                                                                                            | React.ReactElement & { ref?: React.RefCallback\<HTMLElement> } | -                                            |          | -        |
| visible                | 是否显示弹层                                                                                                                                                        | boolean                                                        | false                                        |          | -        |
| onRequestClose         | 弹层请求关闭时触发事件的回调函数，v2 版本第一个参数是 event                                                                                                         | (type: string, e: Event \| React.MouseEvent\<Element>) => void | -                                            |          | -        |
| target                 | 弹层定位的参照元素                                                                                                                                                  | PropTarget                                                     | Position.VIEWPORT                            |          | -        |
| align                  | 弹层相对于参照元素的定位，详见开发指南的 [定位部分](#定位)                                                                                                          | string                                                         | 'tl bl'                                      |          | -        |
| offset                 | 弹层相对于 trigger 的定位的微调，接收数组 [hoz, ver], 表示弹层在 left / top 上的增量 e.g. [100, 100] 表示往右 (RTL 模式下是往左) 、下分布偏移 100px                 | Array\<number>                                                 | [0, 0]                                       |          | -        |
| container              | 渲染组件的容器，如果是函数需要返回 ref，如果是字符串则是该 DOM 的 id，也可以直接传入 DOM 节点                                                                       | PropTarget                                                     | -                                            |          | -        |
| hasMask                | 是否显示遮罩                                                                                                                                                        | boolean                                                        | false                                        |          | -        |
| canCloseByEsc          | 是否支持 esc 按键关闭弹层                                                                                                                                           | boolean                                                        | true                                         |          | -        |
| canCloseByOutSideClick | 点击弹层外的区域是否关闭弹层，不显示遮罩时生效                                                                                                                      | boolean                                                        | true                                         |          | -        |
| canCloseByMask         | 点击遮罩区域是否关闭弹层，显示遮罩时生效                                                                                                                            | boolean                                                        | true                                         |          | -        |
| beforeOpen             | 弹层打开前触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| onOpen                 | 弹层打开时触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| afterOpen              | 弹层打开后触发事件的回调函数，如果有动画，则在动画结束后触发                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| beforeClose            | 弹层关闭前触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| onClose                | 弹层关闭时触发事件的回调函数                                                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| afterClose             | 弹层关闭后触发事件的回调函数，如果有动画，则在动画结束后触发                                                                                                        | (target?: React.ReactNode) => void                             | -                                            |          | -        |
| beforePosition         | 弹层定位完成前触发的事件                                                                                                                                            | () => void                                                     | -                                            |          | -        |
| onPosition             | 弹层定位完成时触发的事件                                                                                                                                            | (config: object, node?: object) => void                        | -                                            |          | -        |
| shouldUpdatePosition   | 是否在每次弹层重新渲染后强制更新定位信息，一般用于弹层内容区域大小发生变化时，仍需保持原来的定位方式                                                                | boolean                                                        | false                                        |          | -        |
| autoFocus              | 弹层打开时是否让其中的元素自动获取焦点                                                                                                                              | boolean                                                        | false                                        |          | -        |
| disableScroll          | 是否禁用页面滚动                                                                                                                                                    | boolean                                                        | false                                        |          | -        |
| cache                  | 隐藏时是否保留子节点                                                                                                                                                | boolean                                                        | false                                        |          | -        |
| safeNode               | 安全节点，当点击 document 的时候，如果包含该节点则不会关闭弹层，如果是函数需要返回 ref，如果是字符串则是该 DOM 的 id，也可以直接传入 DOM 节点，或者以上值组成的数组 | React.ReactNode                                                | -                                            |          | -        |
| wrapperClassName       | 弹层的根节点的样式类                                                                                                                                                | string                                                         | -                                            |          | -        |
| wrapperStyle           | 弹层的根节点的内联样式                                                                                                                                              | React.CSSProperties                                            | -                                            |          | -        |
| animation              | 配置动画的播放方式，支持 \{ in: 'enter-class', out: 'leave-class' \} 的对象参数，如果设置为 false，则不播放动画。请参考 Animate 组件的文档获取可用的动画名          | string \| false \| AnimationObjectType \| undefined            | \{ in: 'expandInDown', out: 'expandOutUp' \} |          | -        |
| v2                     | 开启 v2 版本                                                                                                                                                        | true                                                           | false                                        |          | 1.25     |
| points                 | [v2] align 的数组形式，不能和 align 同时使用                                                                                                                        | Array\<string>                                                 | -                                            |          | 1.25     |
| useCapture             | 是否在捕获阶段监听，适配 react 17 事件模型变更                                                                                                                      | boolean                                                        | -                                            |          | 1.25     |

### Overlay.Popup

| 参数                | 说明                                                                                                      | 类型                                                                   | 默认值                         | 是否必填 |
| ------------------- | --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------ | -------- |
| autoAdjust          | [v2] 浮窗被遮挡时是否自动调整位置                                                                         | boolean                                                                | -                              |          |
| children            | 弹层内容                                                                                                  | React.ReactElement                                                     | -                              |          |
| autoFit             | 弹层是否自适应内容                                                                                        | boolean                                                                | false                          |          |
| visible             | 弹层当前是否显示                                                                                          | boolean                                                                | false                          |          |
| target              | 弹层定位的参照元素                                                                                        | PropTarget                                                             | -                              |          |
| trigger             | 触发弹层显示或隐藏的元素                                                                                  | React.ReactElement                                                     | -                              |          |
| triggerType         | 触发弹层显示或隐藏的操作类型，可以是 'click'，'hover'，'focus'，或者它们组成的数组，如 ['hover', 'focus'] | 'click' \| 'hover' \| 'focus' \| Array\<'click' \| 'hover' \| 'focus'> | 'hover'                        |          |
| triggerClickKeycode | 当 triggerType 为 click 时才生效，可自定义触发弹层显示的键盘码                                            | number \| Array\<number>                                               | [KEYCODE.SPACE, KEYCODE.ENTER] |          |
| defaultVisible      | 弹层默认是否显示                                                                                          | boolean                                                                | false                          |          |
| onVisibleChange     | 弹层显示或隐藏时触发的回调函数，v2 版本第二个参数是 event                                                 | (visible: boolean, type: string \| object, e?: object) => void         | -                              |          |
| disabled            | 设置此属性，弹层无法显示或隐藏                                                                            | boolean                                                                | false                          |          |
| delay               | 弹层显示或隐藏的延时时间（以毫秒为单位），在 triggerType 被设置为 hover 时生效                            | number                                                                 | 200                            |          |
| mouseEnterDelay     | 鼠标放置后的延时显示，单位毫秒 ms, 优先级高于 delay                                                       | number                                                                 | -                              |          |
| mouseLeaveDelay     | 鼠标离开后的延时显示，单位毫秒 ms, 优先级高于 delay                                                       | number                                                                 | -                              |          |
| canCloseByTrigger   | trigger 是否可以关闭弹层                                                                                  | boolean                                                                | true                           |          |
| followTrigger       | 是否跟随 trigger 滚动                                                                                     | boolean                                                                | false                          |          |
| v2                  | 开启 v2 版本                                                                                              | false \| undefined                                                     | -                              |          |
| placement           | [v2] 快捷位置                                                                                             | string                                                                 | 'tr'                           |          |

### Overlay.Popup

| 参数                | 说明                                                                                                      | 类型                                                                   | 默认值                         | 是否必填 |
| ------------------- | --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------ | -------- |
| autoAdjust          | [v2] 浮窗被遮挡时是否自动调整位置                                                                         | boolean                                                                | -                              |          |
| children            | 弹层内容                                                                                                  | React.ReactElement                                                     | -                              |          |
| autoFit             | 弹层是否自适应内容                                                                                        | boolean                                                                | false                          |          |
| visible             | 弹层当前是否显示                                                                                          | boolean                                                                | false                          |          |
| target              | 弹层定位的参照元素                                                                                        | PropTarget                                                             | -                              |          |
| trigger             | 触发弹层显示或隐藏的元素                                                                                  | React.ReactElement                                                     | -                              |          |
| triggerType         | 触发弹层显示或隐藏的操作类型，可以是 'click'，'hover'，'focus'，或者它们组成的数组，如 ['hover', 'focus'] | 'click' \| 'hover' \| 'focus' \| Array\<'click' \| 'hover' \| 'focus'> | 'hover'                        |          |
| triggerClickKeycode | 当 triggerType 为 click 时才生效，可自定义触发弹层显示的键盘码                                            | number \| Array\<number>                                               | [KEYCODE.SPACE, KEYCODE.ENTER] |          |
| defaultVisible      | 弹层默认是否显示                                                                                          | boolean                                                                | false                          |          |
| onVisibleChange     | 弹层显示或隐藏时触发的回调函数，v2 版本第二个参数是 event                                                 | (visible: boolean, type: string \| object, e?: object) => void         | -                              |          |
| disabled            | 设置此属性，弹层无法显示或隐藏                                                                            | boolean                                                                | false                          |          |
| delay               | 弹层显示或隐藏的延时时间（以毫秒为单位），在 triggerType 被设置为 hover 时生效                            | number                                                                 | 200                            |          |
| mouseEnterDelay     | 鼠标放置后的延时显示，单位毫秒 ms, 优先级高于 delay                                                       | number                                                                 | -                              |          |
| mouseLeaveDelay     | 鼠标离开后的延时显示，单位毫秒 ms, 优先级高于 delay                                                       | number                                                                 | -                              |          |
| canCloseByTrigger   | trigger 是否可以关闭弹层                                                                                  | boolean                                                                | true                           |          |
| followTrigger       | 是否跟随 trigger 滚动                                                                                     | boolean                                                                | false                          |          |
| v2                  | 开启 v2 版本                                                                                              | true                                                                   | -                              |          |
| placement           | [v2] 快捷位置                                                                                             | string                                                                 | 'tr'                           |          |

### Overlay.Position

| 参数     | 说明               | 类型                     | 默认值 | 是否必填 |
| -------- | ------------------ | ------------------------ | ------ | -------- |
| children | 弹层内容           | React.ReactElement       | -      |          |
| target   | 弹层定位的参照元素 | PropTarget \| 'viewport' | -      |          |

### Overlay.Gateway

| 参数     | 说明               | 类型                                                                               | 默认值 | 是否必填 |
| -------- | ------------------ | ---------------------------------------------------------------------------------- | ------ | -------- |
| children | 弹层内容           | null \| (React.ReactElement & { ref?: React.RefCallback\<HTMLElement> \| string }) | -      |          |
| target   | 弹层定位的参照元素 | PropTarget                                                                         | -      |          |

### AnimationObjectType

```typescript
export type AnimationObjectType = Record<'in' | 'out', string>;
```

### PropTarget

```typescript
export type Target<T = unknown> =
    | React.ReactInstance
    | string
    | ((param?: T) => React.ReactInstance | Element | Text | Node | null | void | undefined)
    | Element
    | Node
    | Text
    | null
    | false
    | undefined;
```

## 无障碍键盘操作指南

`说明`： 此组件需要结合其他组件使用，会有提示。


---


## pagination

# zh-CN order=1

# 受控分页

受控分页，是指分页组件的状态由父组件维护，组件自身只负责渲染其父组件传递的值，父组件通过 `current` 属性传递当前的值。

# en-US order=1

# Controlled Pagination Component

Controlled Pagination-Component means that the state of the paging component is maintained by the parent component. The component itself is only responsible for rendering the value passed by its parent component. The parent component passes the current value through the `current` attribute.


---


## pagination

# zh-CN order=9

# 下拉框位置

使用`popupProps` prop中的`align`属性设置下拉位置。

# en-US order=9

# Dropdown align

Set dropdown location using `align` property in `popupProps` prop.


---


## pagination

# zh-CN order=10

# 分页按钮链接

可以通过指定 `link` 属性来设置页码按钮的跳转链接，方便 SEO，link 属性的值为一个包含 `{page}` 的模板字符串，Pagination 组件会将该占位符替换为具体的页码数字。

# en-US order=10

# Pagination Button Link

You can set the page link's jump url by specifying the `link` attribute. The value of the SEO, link attribute is a template string containing `{page}`, and the Pagination component replaces the placeholder with a specific page number.


---


## pagination

# zh-CN order=2

# 更多分页

当分页数大于5时，自动展示 `...`

# en-US order=2

# More Pagination

Show `...` when pagination number exceeds 5.


---


## pagination

# zh-CN order=3

# 每页显示

可以通过设置 `pageSize` 属性来指定每页显示的数量。<br>
可以通过设置 `pageSizeSelector` 属性来指定是否显示 每页数量选择 的部件以及部件形状。<br>
可以通过设置 `pageSizeList` 属性来指定 每页显示数量 可选的值。<br>
可以通过设置 `pageSizePosition` 属性来指定 每页显示数量选择 的部件显示在整个组件的开始位置还是结束位置。<br>
可以通过设置 `onPageSizeChange` 属性来指定每页显示的数量变化时的回调函数。<br>
`pageSize` 仅支持受控模式，当设置 `pageSizeSelector` 时，需要同时设置 `pageSize`、`onPageSizeChange` 才能达到效果。

# en-US order=3

# Every Page Display

The `Page Size` property can be set to specify the number of records on the page.<br>
The `pageSizeSelector` property can be set to specify whether to display the number of parts selected per page and the part shape.
The `pageSizeList` property can specify the number of records per page. <br>
By setting the `pageSizePosition` property, you can specify whether the part selected by the display quantity per page is displayed at the beginning or end of the entire component.<br>
The `onPageSizeChange` property can be set to specify the callback function when the number of pages displayed changes.<br>
`pageSize` only supports controlled mode. When setting `pageSizeSelector`, you need to set `pageSize` and `onPageSizeChange` at the same time to achieve the effect.


---


## pagination

# zh-CN order=11

# 配合 react-router 使用

单页应用场景下，Pagination 组件可以使用外部跳转的方法来实现单页内部跳转。

# en-US order=11

# Using With React-Router

In a single-page application scenario, the Pagination component can use external jump methods to implement single-page internal jumps.


---


## pagination

# zh-CN order=6

# 前进后退按钮只显示箭头

可以通过指定 `shape` 属性来设置前进后退按钮箭头的显示方式。

# en-US order=6

# Forward and Back Buttons Only Show Arrows

You can set the forward and back arrow arrows to display by specifying the `shape` property.


---


## pagination

# zh-CN order=4

# 跳转

快速跳转到某一页，可以设置 `false` 来隐藏。

# en-US order=4

# Jump

Quick jump to some page, and can be hidden via setting showJump to false.


---


## pagination

# zh-CN order=8

# 显示总数

分页组件默认不显示总数，你可以通过 totalRender 自定义总数的显示结果。

# en-US order=8

# Display Total Number

By default, the paging component does not display the total number. You can customize the total display result by using totalRender.


---


## pagination

# zh-CN order=5

# 分页尺寸

可以通过指定 `size` 属性来设置分页的尺寸。

# en-US order=5

# Page Size

You can set the paging size by specifying the `size` property.


---


## pagination

# zh-CN order=7

# 简洁/迷你 风格

可以通过指定 `type` 属性来设置分页器的类型。

# en-US order=7

# Type of Pagination

Set the component type by specifying the `type` property.


---


## pagination

# zh-CN order=0

# 非受控分页

非受控分页，是指分页组件的状态由自己维护，组件值的改变可以通过 `onChange` 事件通知父组件，默认值由 `defaultCurrent` 初始化。

# en-US order=0

# Uncontrolled Pagination Component

Uncontrolled Pagination-Component means that the state of the paging component is maintained by itself. Changes to the component values can be notified to the parent component via the `onChange` event. The default value is initialized by `defaultCurrent`.


---


## pagination

# Pagination

-   category: Components
-   family: Navigation
-   chinese: 翻页器
-   cols: 1
-   type: 导航

---

分页器组件。

## 何时使用

在有大量内容展现需要进行分页加载处理的时候。

## API

### Pagination

| 参数             | 说明                                                                                                              | 类型                                                         | 默认值          | 是否必填 |
| ---------------- | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ | --------------- | -------- |
| type             | 分页组件类型                                                                                                      | 'normal' \| 'simple' \| 'mini'                               | 'normal'        |          |
| shape            | 前进后退按钮样式                                                                                                  | 'normal' \| 'arrow-only' \| 'arrow-prev-only' \| 'no-border' | 'normal'        |          |
| size             | 分页组件大小                                                                                                      | 'small' \| 'medium' \| 'large'                               | 'medium'        |          |
| current          | （受控）当前页码                                                                                                  | number                                                       | 1               |          |
| defaultCurrent   | （非受控）初始页码                                                                                                | number                                                       | 1               |          |
| onChange         | 页码发生改变时的回调函数                                                                                          | (current: number, e: object) => void                         | -               |          |
| total            | 总记录数                                                                                                          | number                                                       | 100             |          |
| totalRender      | 总数的渲染函数                                                                                                    | (total: number, range: number[]) => void                     | -               |          |
| pageShowCount    | 页码显示的数量，更多的使用...代替                                                                                 | number                                                       | 5               |          |
| pageSize         | 一页中的记录数                                                                                                    | number                                                       | 10              |          |
| pageSizeSelector | 每页显示选择器类型                                                                                                | false \| 'filter' \| 'dropdown'                              | false           |          |
| pageSizeList     | 每页显示选择器可选值                                                                                              | Array\<number> \| Array\<{ label: string; value: number }>   | [5, 10, 20]     |          |
| pageNumberRender | 自定义页码渲染函数，函数作用于页码button以及当前页/总页数的数字渲染                                               | (index: number) => ReactNode                                 | index =\> index |          |
| pageSizePosition | 每页显示选择器在组件中的位置                                                                                      | 'start' \| 'end'                                             | 'start'         |          |
| useFloatLayout   | 存在每页显示选择器时是否使用浮动布局                                                                              | boolean                                                      | false           |          |
| onPageSizeChange | 每页显示记录数量改变时的回调函数                                                                                  | (pageSize: number) => void                                   | -               |          |
| hideOnlyOnePage  | 当分页数为1时，是否隐藏分页器                                                                                     | boolean                                                      | false           |          |
| showJump         | type 设置为 normal 时，在页码数超过5页后，会显示跳转输入框与按钮，当设置 showJump 为 false 时，不再显示该跳转区域 | boolean                                                      | true            |          |
| link             | 设置页码按钮的跳转链接，它的值为一个包含 \{page\} 的模版字符串，如：http://www.taobao.com/\{page\}                | string                                                       | -               |          |
| popupProps       | 弹层组件属性，透传给Popup                                                                                         | PopupProps                                                   | -               |          |
| selectProps      | 页码选择器下拉组件属性，透传给Select                                                                              | SelectProps                                                  | -               |          |

## 无障碍键盘操作指南

| 按键  | 说明     |
| :---- | :------- |
| Tab   | 切换页数 |
| Space | 按下按钮 |
| Enter | 按下按钮 |


---


## paragraph

# zh-CN order=0

# 基本

最简单的用法。

# en-US order=0

# basic

simple usage


---


## paragraph

# zh-CN order=1

# 长短文本

用于短文本和长文本的区分，短文本的行间距会更小 (一般为三行以内)

# en-US order=1

# long and short text

long for all text, short for those text within three lines


---


## paragraph

# Paragraph

-   category: Components
-   family: General
-   chinese: 段落
-   type: 基本

---

**已废弃，请使用Typography**，段落用于控制页面整体的文本视觉，主要由行间距及文本大小体现。

## 何时使用

-   页面文本展示需要一致体验。
-   一般短文本和长文本的行间距是有差别的，短文本的行间距会更小(一般为三行以内)

## API

### Paragraph

| 参数      | 说明                              | 类型                | 默认值   | 是否必填 |
| --------- | --------------------------------- | ------------------- | -------- | -------- |
| className | 额外的样式名 会附加到 root dom 上 | string              | -        |          |
| type      | 什么方式展示段落                  | 'long' \| 'short'   | 'long'   |          |
| size      | 组件大小。                        | 'medium' \| 'small' | 'medium' |          |


---


## progress

# zh-CN order=0

# 基本进度条

普通模式的进度条，通过 `percent` 属性指定进度，通过 `textRender` 控制右侧文本信息的展示，
通过 `hasBorder` 属性设置组件是否包含边框。

# en-US order=0

# Basic progress bar

A basic progress bar, using `percent` to control current progress, and control the tail text with `textRender`.


---


## progress

# zh-CN order=1

# 圆形进度条

通过 `shape` 属性可以改变进度指示器的外观，当取值为 `circle` 时为圆形进度条。

# en-US order=1

# Progress circle

A simple progress circle.


---


## progress

# zh-CN order=5

# 颜色

通过 `color` 属性可以改变进度条的颜色。Progress 有三个API可以改变进度条的颜色,其优先级为 color > progressive > state。

# en-US order=5

# Color

Use `color` prop to controll progress bar color. The Progress Component has three APIs which can controll the color of progress bar and it's priority: color > progressive > state.


---


## progress

# zh-CN order=6

# 动态展示

此时为增强模式的进度条，会根据当前进度展示不同的样式。注: css animation完成需要时间, 数据调整过于频繁会导致显示延迟。

# en-US order=6

# Dynamic

The dynmaic exmaple. Attention: Animation require time to finish, so changing percent too frequently may cause display delay.


---


## progress

# zh-CN order=7

# 自定义百分比信息

`textRender` 控制百分比信息的展示,通过自定义`textRender`个性化百分比渲染. 下面给一个 百分比进度取2位,当达到100%是显示Icon的progressbar.

# en-US order=7

# Custom Percentage

we can define how Percentage text to display by using `textRender`.
The exapme below will show a progressbar with accuracy of 2 decimal places and done icon when reached 100%.


---


## progress

# zh-CN order=4

# Progressive

当开启 `progressive` 模式时，Progress 组件会根据自身的进度自动设置展现的颜色值。
注意，此时会忽略用户设置的 `state` 的属性值。

# en-US order=4

# Progressive

Progressive progresses.


---


## progress

# zh-CN order=2

# 尺寸

可以通过 `size` 属性制定进度条的大小。

# en-US order=2

# Size

Change the size of progress.


---


## progress

# zh-CN order=3

# 进度条不同状态

用户可以通过 `state` 属性自定义当前进度的展现状态，可取值为 `normal`, `success`, `error` 分别表示普通、成功、失败这三种状态。

# en-US order=3

# State

Change the state of Progress by `state`, supporting `normal`, `success`, `error`.


---


## progress

# Progress

-   category: Components
-   family: DataDisplay
-   chinese: 进度指示器
-   type: 展示

---

展示操作的当前进度。

## 何时使用

在操作需要较长时间才能完成时，为用户显示该操作的当前进度和状态。

-   操作在后台运行，需要耗费一定的客户端等待时间。
-   操作需要展示一个完成进度的百分比。

## API

### Progress

| 参数            | 说明                                                                                                                              | 类型                                                           | 默认值                                    | 是否必填 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ----------------------------------------- | -------- |
| shape           | 形态                                                                                                                              | 'circle' \| 'line'                                             | 'line'                                    |          |
| size            | 尺寸                                                                                                                              | 'small' \| 'medium' \| 'large'                                 | 'medium'                                  |          |
| percent         | 所占百分比                                                                                                                        | number                                                         | 0                                         |          |
| state           | 进度状态, 显示优先级: color \> progressive \> state                                                                               | 'normal' \| 'success' \| 'error'                               | 'normal'                                  |          |
| progressive     | 是否为色彩阶段变化模式, 显示优先级: color \> progressive \> state                                                                 | boolean                                                        | false                                     |          |
| hasBorder       | 是否添加 Border（只适用于 Line Progress)                                                                                          | boolean                                                        | false                                     |          |
| textRender      | 文本渲染函数<br/><br/>**签名**:<br/>**参数**:<br/>_percent_: 当前的进度信息<br/>_option_: 额外的参数<br/>**返回值**:<br/>文本节点 | (percent: number, option?: {rtl?: boolean}) => React.ReactNode | percent =\> \`$\{Math.floor(percent)\}%\` |          |
| color           | 进度条颜色, 显示优先级: color \> progressive \> state                                                                             | string                                                         | -                                         |          |
| backgroundColor | 背景色                                                                                                                            | string                                                         | -                                         |          |


---


## radio

# zh-CN order=8

# 无障碍支持

通过`aria-labelledby`给 Group 设置辅助技术可及的文本，按键请参考后文[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=8

# Accessibility

Please refer to `ARIA and KeyBoard`.


---


## radio

# zh-CN order=0

# 基本

使用 `Radio` 渲染的基本组件。

# en-US order=0

# Basic Usage

Basic components rendered using `Radio`.


---


## radio

# zh-CN order=6

# 按钮样式与大小

使用 `RadioGroup` 渲染的组，通过设置 `shape="button"` 可以让组件以按钮形式展示，同时可以通过 `size` 来控制组件大小。

# en-US order=6

# The components display as a button shape

Groups that are rendered using `RadioGroup` can set the component to be displayed as a button by setting `shape="button"`, and the size of the component can be controlled via `size`.


---


## radio

# zh-CN order=9&debug=true

# 受控组件

使用 `RadioGroup` 渲染的组，通过设置 `value` 属性可以让组件变成[受控组件](https://facebook.github.io/react/docs/forms.html#controlled-components)。

# en-US order=9&debug=true

# Controlled Component

Groups rendered using `RadioGroup` can make the component a [controlled component] by setting the `value` property (https://facebook.github.io/react/docs/forms.html#controlled-components).


---


## radio

# zh-CN order=2

# 传入数组配置

通过配置 `dataSource` 参数来渲染单选框分组，数组中对象元素支持配置 radio 属性。

# en-US order=2

# DataSource Usage

Groups that are rendered using `RadioGroup` can set the component using `dataSource`.


---


## radio

# zh-CN order=5

# 垂直展示

垂直展示`<Radio.Group>`，配合更多输入框。仅适用于非 Button 样式的`<Radio.Group>`。

# en-US order=5

# Direction

Vertical `Radio.Group`, with more `radios`.


---


## radio

# zh-CN order=3

# 禁用状态

`Radio`禁用状态。

# en-US order=3

# Disabled

Disabled state of `Radio`.


---


## radio

# zh-CN order=1

# 单选分组

使用 `<Radio.Group>` 渲染 `<Radio>` 分组，选项互斥。

# en-US order=1

# Group Radio

Grouping `<Radio>` with `<Radio.Group>`.


---


## radio

# zh-CN order=4

# 预览状态

`Radio`预览状态。

# en-US order=4

# isPreview

Preview state of `Radio`.


---


## radio

# zh-CN order=10&debug=true

# 非受控组件

使用 `RadioGroup` 渲染的组，通过设置 `defaultValue` 属性可以让组件变成[非受控组件](https://facebook.github.io/react/docs/forms.html#uncontrolled-components)。

# en-US order=10&debug=true

# Uncontrolled Component

Groups rendered using `RadioGroup` can be made to become [uncontrolled component] by setting the `defaultValue` property (https://facebook.github.io/react/docs/forms.html#uncontrolled-components).


---


## radio

# zh-CN order=7

# 使用 Grid 快速布局

使用 `Grid` 布局 `RadioGroup` 中的选项。

# en-US order=7

# Grid Layout

Use the options in the `Grid` layout `RadioGroup`.


---


## radio

# Radio

-   category: Components
-   family: DataEntry
-   chinese: 单选框
-   type: 表单

---

单选框。

## 何时使用

-   单选框允许用户从一个数据集中选择单个选项。面向用户需要并排看到所有的可选项，并使用单选框进行排他操作的场景。

-   对于选项过多的场景，考虑使用下拉列表，相对于显示所有的选项占用更少的空间。

## API

### Radio

| 参数           | 说明                                                                                                                                           | 类型                                                                    | 默认值 | 是否必填 |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | ------ | -------- |
| id             | 组件 input 的 id                                                                                                                               | string                                                                  | -      |          |
| checked        | 设置 radio 是否选中                                                                                                                            | boolean                                                                 | -      |          |
| defaultChecked | 设置 radio 是否默认选中                                                                                                                        | boolean                                                                 | -      |          |
| label          | 通过属性配置 label                                                                                                                             | React.ReactNode                                                         | -      |          |
| onChange       | 选中状态变化时触发的事件<br/><br/>**签名**:<br/>**参数**:<br/>_checked_: 是否选中<br/>_event_: DOM 事件                                        | (checked: boolean, event: React.ChangeEvent\<HTMLInputElement>) => void | -      |          |
| onMouseEnter   | 鼠标进入 enter 事件                                                                                                                            | (e: React.MouseEvent\<HTMLInputElement>) => void                        | -      |          |
| onMouseLeave   | 鼠标离开事件                                                                                                                                   | (e: React.MouseEvent\<HTMLInputElement>) => void                        | -      |          |
| disabled       | radio 是否被禁用                                                                                                                               | boolean                                                                 | -      |          |
| value          | radio 的 value                                                                                                                                 | RadioValue                                                              | -      |          |
| name           | 表单项 name                                                                                                                                    | string                                                                  | -      |          |
| isPreview      | 是否开启预览态                                                                                                                                 | boolean                                                                 | -      |          |
| renderPreview  | 自定义预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_checked_: 是否选中<br/>_props_: 所有传入的参数<br/>**返回值**:<br/>渲染内容 | (checked: boolean, props: RadioProps) => React.ReactNode                | -      |          |

### Radio.Group

| 参数          | 说明                                                                                                                                               | 类型                                                                        | 默认值   | 是否必填 |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | -------- | -------- |
| name          | 表单 name                                                                                                                                          | string                                                                      | -        |          |
| value         | radio group 的选中项的值（受控）                                                                                                                   | RadioValue                                                                  | -        |          |
| defaultValue  | radio group 的默认值（非受控）                                                                                                                     | RadioValue                                                                  | -        |          |
| component     | 设置标签类型                                                                                                                                       | React.ElementType                                                           | 'div'    |          |
| onChange      | 选中值改变时的事件<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 选中的值<br/>_event_: Dom 事件对象                                                | (value: RadioValue, event: React.ChangeEvent\<HTMLInputElement>) => void    | -        |          |
| disabled      | 表示 radio 被禁用                                                                                                                                  | boolean                                                                     | -        |          |
| shape         | 展示类型                                                                                                                                           | 'normal' \| 'button'                                                        | -        |          |
| size          | 与 `shape` 属性配套使用，shape 设为 button 时有效                                                                                                  | 'large' \| 'medium' \| 'small'                                              | 'medium' |          |
| dataSource    | 可选项列表                                                                                                                                         | Array\<RadioValue> \| Array\<RadioValueItem>                                | -        |          |
| children      | 通过子元素方式设置内部 radio                                                                                                                       | React.ReactNode                                                             | -        |          |
| direction     | 子项目的排列方式                                                                                                                                   | 'hoz' \| 'ver'                                                              | -        |          |
| isPreview     | 是否开启预览态                                                                                                                                     | boolean                                                                     | -        |          |
| renderPreview | 自定义预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_previewed_: 预览的数据项<br/>_props_: 预览项的参数<br/>**返回值**:<br/>渲染内容 | (previewed: RadioValueItem \| object, props: GroupProps) => React.ReactNode | -        |          |

### RadioValueItem

| 参数     | 说明 | 类型            | 默认值 | 是否必填 |
| -------- | ---- | --------------- | ------ | -------- |
| label    | -    | React.ReactNode | -      |          |
| value    | -    | RadioValue      | -      | 是       |
| disabled | -    | boolean         | -      |          |

### RadioValue

```typescript
export type RadioValue = string | number | boolean;
```

## 无障碍键盘操作指南

| 按键 | 说明                                                                                                         |
| :--- | :----------------------------------------------------------------------------------------------------------- |
| Tab  | 获取焦点，如果没有任何选中就是第一个，之后可以空格选中。如果有选中的就聚焦到选中项，然后通过左右键直接选中。 |


---


## range

# zh-CN order=0

# 基本

基本滑块，当 `slider` 为 `double` 时，渲染为双滑块。当 `disabled` 为 `true` 时，滑块处于不可用状态。

# en-US order=0

# Basic

Basic usage. When `slider` is `double`, render two sliders; when `disabled` is `true`, the slider is unusable.


---


## range

# zh-CN order=3

# 事件

onChange, onProcess事件

# en-US order=3

# Change

onChange,onProcess callbacks


---


## range

# zh-CN order=1

# 范围与 step

与 number-picker 结合

# en-US order=1

# Basic

Used with number-picker to set the icon.


---


## range

# zh-CN order=0

# 固定宽度滑动

默认双滑块(`slider` 为 `double`)，且指定 `defaultValue`为区间值下可用。范围不可被改变，拖动所选区域改变始末滑块位置。

# en-US order=0

# fixedWidth

It means `slider` is `double`, and `defaultValue` is a interval. The scope can not be changed, drag the selected area to change the position of the start and end slider.


---


## range

# zh-CN order=1

# 刻度及标识

通过 `marks` 属性设置刻度及标识。

# en-US order=1

# Scale and Marks

Use `marks` to set marks


---


## range

# zh-CN order=7

# 选择态反转

设置 reverse 为true, 选中态会反转。

# en-US order=7

# Reverse

When reverse is set to true, the selected part is reversed.


---


## range

# zh-CN order=5

# 自定义滑块标签

通过 tipRender 自定义滑块标签提示

# en-US order=5

# tipRender

tipRender demo.


---


## range

# Range

-   category: Components
-   family: DataEntry
-   chinese: 区段选择器
-   type: 表单

---

区间选择

## 何时使用

滑块控件(Sliders，简称滑块)可以让我们通过在连续或间断的区间内滑动锚点来选择一个合适的数值。区间最小值放在左边，对应的，最大值放在右边。滑块(Sliders)可以在滑动条的左右两端设定图标来反映数值的强度。这种交互特性使得它在设置诸如音量、亮度、色彩饱和度等需要反映强度等级的选项时成为一种极好的选择。

## 如何使用

-   onChange是和value进行配置做受控处理的。onChange在滑动过程中不会触发，滑动停止后会触发。
-   onProcess不建议内部做setState 进行受控，因为会频繁触发，整个滑动过程中会一直触发。

## API

### Range

| 参数           | 说明                                                                                                                                                                        | 类型                                                                       | 默认值            | 是否必填 |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ----------------- | -------- |
| slider         | 滑块个数<br/><br/>**可选值**:<br/>'single'(单个)<br/>'double'(两个)                                                                                                         | 'single' \| 'double'                                                       | 'single'          |          |
| min            | 最小值                                                                                                                                                                      | number                                                                     | 0                 |          |
| max            | 最大值                                                                                                                                                                      | number                                                                     | 100               |          |
| step           | 步长，取值必须大于 0，并且可被 (max - min) 整除                                                                                                                             | number                                                                     | 1                 |          |
| value          | 设置当前取值。当 `slider` 为 `single` 时，使用 `Number`，否则用 `[Number, Number]`                                                                                          | RangeValueType                                                             | -                 |          |
| defaultValue   | 设置初始取值。当 `slider` 为 `single` 时，使用 `Number`，否则用 `[Number, Number]`                                                                                          | RangeValueType                                                             | -                 |          |
| marks          | 刻度数值显示逻辑（false 代表不显示，array 枚举显示的值，number 代表按 number 平分，object 表示按 key 划分，value 值显示）                                                   | false \| number \| Array\<number> \| Record\<number, string>               | false             |          |
| marksPosition  | marks显示在上方('above')or下方('below')<br/><br/>**可选值**:<br/>'above', 'below'                                                                                           | 'above' \| 'below'                                                         | 'above'           |          |
| disabled       | 值为 `true` 时，滑块为禁用状态                                                                                                                                              | boolean                                                                    | false             |          |
| onChange       | 当 Range 的值发生改变后，会触发 onChange 事件，并把改变后的值作为参数传入, 如果设置了value, 要配合此函数做受控使用<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 改变后的值 | (value: RangeValueType) => void                                            | () =\> void       |          |
| onProcess      | 滑块拖动的时候触发的事件,不建议在这里setState, 一般情况下不需要用, 滑动时有特殊需求时使用<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 改变后的值                          | (value: RangeValueType) => void                                            | () =\> void       |          |
| hasTip         | 是否显示 tip                                                                                                                                                                | boolean                                                                    | true              |          |
| tipRender      | 自定义 tip 显示内容<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 改变后的值<br/>**返回值**:<br/>React.ReactNode                                                            | (value: number \| string) => React.ReactNode                               | (value) =\> value |          |
| reverse        | 选中态反转                                                                                                                                                                  | boolean                                                                    | false             |          |
| pure           | 是否pure render                                                                                                                                                             | boolean                                                                    | false             |          |
| fixedWidth     | 是否为拖动线段类型，默认slider为double, defaultValue必传且指定区间                                                                                                          | boolean                                                                    | false             |          |
| tooltipVisible | tooltip是否默认展示                                                                                                                                                         | boolean                                                                    | false             |          |
| isPreview      | 是否为预览态                                                                                                                                                                | boolean                                                                    | false             |          |
| renderPreview  | 预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 改变后的值<br/>_props_: RangeProps<br/>**返回值**:<br/>React.ReactNode                                 | (value: RangeValueType \| undefined, props: RangeProps) => React.ReactNode | -                 |          |

### RangeValueType

```typescript
export type RangeValueType = number | [number, number];
```

## 无障碍键盘操作指南

| 按键        | 说明             |
| :---------- | :--------------- |
| Right Arrow | 控制滑块往右移动 |
| Left Arrow  | 控制滑块向左移动 |
| Tab         | 切换滑动条       |


---


## rating

# zh-CN order=5

# 无障碍支持

组件内置了部分支持无障碍, 但是额外需要开发者手动事情才能完整支持无障碍：给 Rating 传入一个id，就可以支持语音提示当前选择的评分。注意：如果一个页面上有多个 Rating，id 属性一定不能相同。

# en-US order=5

# Accessibility

To Support accessibility, you should assign an id prop to Rating. Notice: Don't assign same id prop for more than one Rating.


---


## rating

# zh-CN order=0

# 基本

最简单的用法。

# en-US order=0

# Basic

Basic usage.


---


## rating

# zh-CN order=4

# 清除

支持允许或者禁用清除。

# en-US order=4

# Clear star

Support set allow to clear star when click again.


---


## rating

# zh-CN order=4

# 只读模式

设置 `disabled` 属性后，评分组件仅展示模式，不可选择。

# en-US order=4

# Read-only Mode

Rating component can only display score when you set `disabled` attribute.


---


## rating

# zh-CN order=5

# 等级提示

添加 `showGrade` 属性，使评分组件具有等级提示信息。

# en-US order=5

# Grade Prompt

Rating component display grade tips when you set `showGrade` attribute.


---


## rating

# zh-CN order=2

# 半星评分

默认情况下评分组件只支持整数评分，通过开启 `allowHalf` 属性可以支持半星评分。

# en-US order=2

# Half-star Rating

Rating component only support integer score in default situation, bu you can set `allowHalf` attribute to support half star.


---


## rating

# zh-CN order=5

# 预览态

设置 `isPreview` 和 `renderPreview` 属性后，评分组件仅展示模式，渲染自定义内容。

# en-US order=5

# Preview Mode

Rating component can only display score when you set `isPreview` and `renderPreview` attribute, and render the custom content.


---


## rating

# zh-CN order=1

# 尺寸

通过 `size` 属性可以控制评分组件的大小，支持三种尺寸 `small`, `medium`, `large`。
默认尺寸为 `medium` 。

# en-US order=1

# Size

You can control the size of rating component by `size` attribute, and there are three options: `small`, `medium`, `large`, the default value is `medium`.


---


## rating

# Rating

-   category: Components
-   family: DataEntry
-   chinese: 评分
-   type: 基本

---

评分组件通常用于用户反馈场景。

## API

### Rating

| 参数          | 说明                                                                                                                                                                               | 类型                                                   | 默认值   | 是否必填 |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ | -------- | -------- |
| defaultValue  | 默认值                                                                                                                                                                             | number                                                 | -        |          |
| value         | 值（受控模式）                                                                                                                                                                     | number                                                 | -        |          |
| size          | 尺寸                                                                                                                                                                               | 'small' \| 'medium' \| 'large'                         | 'medium' |          |
| count         | 评分的总数                                                                                                                                                                         | number                                                 | 5        |          |
| showGrade     | 是否显示 grade                                                                                                                                                                     | boolean                                                | false    |          |
| allowHalf     | 是否允许半星评分                                                                                                                                                                   | boolean                                                | -        |          |
| allowClear    | 是否允许再次点击后清除                                                                                                                                                             | boolean                                                | false    |          |
| onChange      | 用户点击评分时触发的回调                                                                                                                                                           | (value: number) => void                                | -        |          |
| onHoverChange | 用户 hover 评分时触发的回调                                                                                                                                                        | (value?: number) => void                               | -        |          |
| disabled      | 是否禁用                                                                                                                                                                           | boolean                                                | false    |          |
| isPreview     | 是否为预览态                                                                                                                                                                       | boolean                                                | false    |          |
| renderPreview | 预览态模式下渲染的内容（isPreview 时必传，否则预览不生效）<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 评分值<br/>_props_: 组件参数对象<br/>**返回值**:<br/>预览模式下的渲染内容 | (value: number, props: RatingProps) => React.ReactNode | -        |          |
| readAs        | 评分文案生成方法，传入 id 支持无障碍时，读屏软件可读<br/><br/>**签名**:<br/>**参数**:<br/>_val_: 当前分值<br/>**返回值**:<br/>该分值的渲染文案                                     | (val: number) => React.ReactNode                       | -        |          |
| type          | -                                                                                                                                                                                  | string                                                 | -        |          |

## 无障碍键盘操作指南

| 按键        | 说明         |
| :---------- | :----------- |
| Up Arrow    | 增加星级评分 |
| Down Arrow  | 减少星级评分 |
| Right Arrow | 增加星级评分 |
| Left Arrow  | 减少星级评分 |


---


## responsive-grid

# zh-CN order=0

# 基本

简单的栅格布局展示，Fusion Next推荐以PC为主要开发场景，自适配平板、手机端。默认使用12栅格布局。

只需进行如下设置，页面内容就可以根据自适应，遵循 12-8-4 设计原则。

-   将子元素按顺序排布；
-   指定子元素所占的比例（默认为1，即1/12）；
-   并配合屏幕大小（或ua信息）的改变设置device。

# en-US order=0

# Basic Usage

Simple usage of ResponsiveGrid component.


---


## responsive-grid

# ResponsiveGrid

-   category: Components
-   family: General
-   chinese: 栅格布局
-   type: 展示
-   version: 1.19

---

栅格布局，使用`display: grid`，1.19.0+ 添加本组件，目前不支持IE。

## 如何使用

-   PC first，其他屏幕支持自适应，因此默认情况下 `device` 处于 `desktop` 模式，此时 `columns` 为12列；
-   更改 `device` 参数为 `tablet` 后 `columns` 为8列；
-   更改 `device` 参数为 `phone` 后 `columns` 为4列，同时 Cell会根据内置规则进行自适应调配。

## FAQ

### 为何嵌套自定义组件，间距没有生效？

自定义组件的间距是 `ResponsiveGrid` 算出来，同style透传给子组件的，因此子组件需要至少透传style属性；

```jsx
// wrong
function Foo() {
    return <div />;
}

// correct
function Foo({ style }) {
    return <div style={style} />;
}
```

## API

### ResponsiveGrid

| 参数      | 说明                                                     | 类型                              | 默认值    | 是否必填 |
| --------- | -------------------------------------------------------- | --------------------------------- | --------- | -------- |
| device    | 设备，用来做自适应，默认为 PC                            | 'phone' \| 'tablet' \| 'desktop'  | 'desktop' |          |
| columns   | 分为几列， 默认是 12 列                                  | number \| string                  | '12'      |          |
| gap       | 每个 cell 之间的间距， [bottom&top, right&left]          | Spacing                           | -         |          |
| component | 设置标签类型                                             | keyof React.JSX.IntrinsicElements | 'div'     |          |
| dense     | 是否开启紧密模式，开启后尽可能能紧密填满，尽量不出现空格 | boolean                           | 'false'   |          |

### ResponsiveGrid.Cell

| 参数      | 说明           | 类型                                                                                         | 默认值 | 是否必填 |
| --------- | -------------- | -------------------------------------------------------------------------------------------- | ------ | -------- |
| colSpan   | 横向，占据几列 | \| number<br/> \| {<br/> desktop?: number;<br/> tablet?: number;<br/> phone?: number;<br/> } | -      |          |
| rowSpan   | 纵向，占据几行 | number                                                                                       | -      |          |
| component | 设置标签类型   | keyof React.JSX.IntrinsicElements                                                            | 'div'  |          |


---


## search

# zh-CN order=6

# 无障碍支持

按下Enter键调用`onSearch`事件去处理,请参考[无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=6

# Accessibility

Press the Enter key to call the `onSearch` event handle,Please refer to `ARIA and KeyBoard`.


---


## search

# zh-CN order=0

# 基础用法

# en-US order=0

# Basic usage


---


## search

# zh-CN order=4

# 联想

# en-US order=4

# Sugguest Box


---


## search

# zh-CN order=5

# 自定义弹层

自定义下拉框内容。

# en-US order=5

# Custom Dropdown

custom dropdown content


---


## search

# zh-CN order=3

# 下拉框

带下拉框的用法。可以设置onFilterChange事件

# en-US order=3

# Filter

Filter dropdown, use with onFilterChange event


---


## search

# zh-CN order=2

# 大小

通过size进行大小设置，支持large、medium

# en-US order=2

# Size

Filter dropdown, use with onFilterChange.


---


## search

# zh-CN order=1

# 类别

简单用法

# en-US order=1

# type

Simple Usage


---


## search

# Search

-   category: Components
-   family: DataEntry
-   chinese: 搜索
-   type: 表单
-   cols: 1

---

搜索组件。

## 何时使用

页面、表单数据搜索时使用。

## API

### Search

| 参数                   | 说明                                               | 类型                                                            | 默认值   | 是否必填 |
| ---------------------- | -------------------------------------------------- | --------------------------------------------------------------- | -------- | -------- |
| size                   | 大小                                               | 'large' \| 'medium'                                             | 'medium' |          |
| value                  | 搜索框数值                                         | string \| number                                                | -        |          |
| defaultValue           | 搜索框默认值                                       | string                                                          | -        |          |
| placeholder            | 默认提示                                           | string                                                          | -        |          |
| autoWidth              | 下拉菜单是否与选择器对齐                           | boolean                                                         | -        |          |
| label                  | 自定义内联 label                                   | React.ReactNode                                                 | -        |          |
| hasClear               | 是否显示清除按钮                                   | boolean                                                         | -        |          |
| state                  | 校验状态                                           | 'error' \| 'loading'                                            | -        |          |
| readOnly               | 是否只读，只读模式下可以展开弹层但不能选           | boolean                                                         | -        |          |
| disabled               | 是否禁用                                           | boolean                                                         | -        |          |
| visible                | 自定义渲染的的下拉框                               | boolean                                                         | -        |          |
| defaultVisible         | 弹层初始化是否显示                                 | boolean                                                         | -        |          |
| onVisibleChange        | 弹层显示或隐藏时触发的回调                         | (visible: boolean) => void                                      | -        |          |
| popupContainer         | 弹层挂载的容器节点                                 | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement) | -        |          |
| popupClassName         | 弹层的 className                                   | string                                                          | -        |          |
| popupStyle             | 弹层的内联样式                                     | React.CSSProperties                                             | -        |          |
| popupProps             | 添加到弹层上的属性                                 | PopupProps                                                      | -        |          |
| popupContent           | 自定义渲染的的下拉框                               | React.ReactNode                                                 | -        |          |
| filterLocal            | 是否使用本地过滤，在数据源为远程的时候需要关闭此项 | boolean                                                         | -        |          |
| filter                 | 选择器                                             | SelectProps['dataSource']                                       | -        |          |
| useVirtual             | 是否开启虚拟滚动模式                               | boolean                                                         | -        |          |
| dataSource             | 搜索框下拉联想列表                                 | AutoCompleteProps['dataSource']                                 | -        |          |
| itemRender             | 渲染 MenuItem 内容的方法                           | (item: Item) => React.ReactNode                                 | -        |          |
| onChange               | 输入关键字时的回掉                                 | AutoCompleteProps['onChange']                                   | -        |          |
| fillProps              | 填充到选择框里的值的 key，默认是 value             | string                                                          | -        |          |
| prefix                 | 样式前缀                                           | string                                                          | -        |          |
| shape                  | 形状                                               | 'normal' \| 'simple'                                            | 'normal' |          |
| type                   | 类型                                               | 'primary' \| 'secondary' \| 'normal' \| 'dark'                  | 'normal' |          |
| onSearch               | 点击搜索按钮触发的回调                             | (value: string, filterValue?: string) => void                   | -        |          |
| defaultFilterValue     | 选择器默认值                                       | string                                                          | -        |          |
| filterValue            | 选择器值                                           | string                                                          | -        |          |
| onFilterChange         | 选择器发生变化时回调                               | (filter: string) => void                                        | -        |          |
| searchText             | button 的内容                                      | React.ReactNode                                                 | -        |          |
| filterProps            | 选择器的props                                      | SelectProps                                                     | -        |          |
| buttonProps            | 按钮的额外属性                                     | ButtonProps                                                     | -        |          |
| hasIcon                | 是否显示搜索按钮                                   | boolean                                                         | -        |          |
| icons                  | 可配置的icons，包括 search 等                      | {<br/> search?: React.ReactNode;<br/> }                         | -        |          |
| followTrigger          | 是否跟随滚动                                       | boolean                                                         | -        |          |
| autoHighlightFirstItem | 是否自动高亮第一个元素                             | boolean                                                         | -        |          |
| onToggleHighlightItem  | 键盘上下键切换菜单高亮选项的回调                   | AutoCompleteProps['onToggleHighlightItem']                      | -        |          |

## Search 内部函数(通过refs获取)

| 参数  | 说明                                                                                                                                             | 类型     | 默认值 |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------- | ------ |
| focus | 获取焦点<br><br>**签名**:<br> Function(start:Number, end: Number)<br>**参数**:<br>_start_: {Number} 光标起始位置<br>_end_: {Number} 选择结束位置 | Function |        |

## 无障碍键盘操作指南

| 按键  | 说明             |     |
| :---- | :--------------- | --- |
| Enter | 触发onSearch事件 |     |


---


## select

# zh-CN order=16

# 无障碍支持

当聚焦在组件上时，通过`aria-labelledby`对组件进行描述。关于键盘操作请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=16

# Accessibility

When focusing on a component, the component is described by `aria-labelledby`. Please refer to `ARIA and KeyBoard` for keyboard operation.


---


## select

# zh-CN order=3&debug=true

# 调整标签尺寸

标签尺寸是否和`Select`尺寸保持一致（仅在`多选/标签`模式下生效），默认false。

# en-US order=3&debug=true

# Adjust Tag Size

Set if the size of tag should be the same as select when mode is `multiple` or `tag`


---


## select

# zh-CN order=0

# 基本使用

最基本的使用、带清除、搜索功能的展示

# en-US order=0

# Basic

simple usage, has clear, show search


---


## select

# zh-CN order=9

# 输入框辅助完成

`AutoComplete` 继承了 `Input` 的能力，并在其基础上增加了 autoComplete 的功能。
对于设置为`AutoComplete`为off不生效对的情况，可以参考 [MDN](https://developer.mozilla.org/zh-CN/docs/Web/Security/Securing_your_site/Turning_off_form_autocompletion]) 中进行设置。

# en-US order=9

# autocomplete

`AutoComplete` inherits the capabilities of `Input` and adds autoComplete functionality to it.


---


## select

# zh-CN order=10&debug=true

# 自动完成大小

`AutoComplete` 大小、disabled、清除

# en-US order=10

# Basic

`AutoComplete` api of size/disabled/hasClear


---


## select

# zh-CN order=11

# 辅助输入获取远程数据

使用动态数据填充 AutoComplete, 设置 `filterLocal` 为 false

# en-US order=11

# Dynamic data

By set `filterLocal` to false, so you can use AutoComplete with dynamic data.


---


## select

# zh-CN order=7

# 自定义菜单

通过 `itemRender` 和 `valueRender` (仅 Select) 自定义渲染的节点内容。

# en-US order=7

# custom menu

custom render Item by api of `itemRender` and `valueRender` (only support by Select)


---


## select

# zh-CN order=8

# 定制菜单布局

通过 `MenuProps` 自定义 `Select` 弹窗的头部和底部（注意 `MenuProps.header` 不能与 `hasSelectAll` 同时出现, `MenuProps.header` 优先级更高）

# en-US order=8

# custom popup render

simple usage


---


## select

# zh-CN order=9

# 弹层定制

通过 popupContent 定制 Select 弹层， Select 使用 popupContent 中渲染出的 item 的 value 作为菜单项的key，如果没有提供或者自定义渲染 key 请使用 valueRender

# en-US order=9

# custom popup

custom Popup by `popupContent`


---


## select

# zh-CN order=6

# 自定义 value 展示

自定义 value 展示

# en-US order=6

# custom value

custom value render


---


## select

# zh-CN order=3

# 最大数量

多选模式下通过 `maxTagCount` 控制选择的个数，通过 `maxTagPlaceholder` 控制选择的 hover 样式

# en-US order=3

# max count

multiple select


---


## select

# zh-CN order=0&debug=true

# 基本使用

最基本的使用、带清除、搜索功能的展示

# en-US order=0

# Basic

simple usage, has clear, show search


---


## select

# zh-CN order=2

# 多选

多选模式, 通过 `showSearch` 可以开启搜索, 但搜索值不可用作选项

# en-US order=2

# Multiple

multiple select, use `showSearch` to search, search value can not to be a option (different with mode=tag);


---


## select

# zh-CN order=2

# DS

多选模式, 通过 `showSearch` 可以开启搜索, 但搜索值不可用作选项

# en-US order=2

# 选择

multiple select, use `showSearch` to search, search value can not to be a option (different with mode=tag);


---


## select

# zh-CN order=4&debug=true

# 选择器

演示了 Select 的多种形态.

# en-US order=4

# Select

api usage of select


---


## select

# zh-CN order=4

# 级联选择

使用 Select 构建级联选择框

# en-US order=4

# cascader select

make a cascader by select


---


## select

# zh-CN order=7

# 前后缀

Select 增加前后缀

# en-US order=7

# prefix and suffix

add prefix or suffix to select


---


## select

# zh-CN order=5

# 分组

使用 OptionGroup 针对选项进行分组

# en-US order=5

# Group

use OptionGroup


---


## select

# zh-CN order=15

# 滚动到底部加载

通过监控 menu的 onScroll 滚动到底部的时候自动加载 dataSource

# en-US order=15

# scroll loading data

loading dataSource while scroll to bottom


---


## select

# zh-CN order=7

# 远程搜索

使用 `showSearch` 显示搜索框，如果需要动态更新 dataSource，需要关闭 filterLocal

# en-US order=7

# Remote Search

search box will show by `showSearch`，if `dataSource` is update by remote api，you need to set `filterLocal=false`


---


## select

# zh-CN order=3

# 标签

标签模式，输入的内容可以作为选项, 可以通过 dataSource 的 color 设置选中标签的颜色

# en-US order=1

# Tag

Tag mode, can use input value as option, selected tag color can set with dataSource's color


---


## select

# zh-CN order=8

# 对象数据

`useDetailValue` 把 `value` `onChange` 第一个参数 从字符串变成对象

# en-US order=8

# useDetailValue

`useDetailValue` change `value` `onChange` from string to object


---


## select

# zh-CN order=15

# 大数据

select 开启无限滚动可支持大数据的 dataSource，保证性能

# en-US order=15

# virtual-select

select with virtual list


---


## select

# Select

-   category: Components
-   family: DataEntry
-   chinese: 选择器
-   type: 表单

---

选择组件。

## 何时使用

-   Select 用于替代原生 select，在限定的可选项内进行选择，核心能力是 `选择`
-   AutoComplete 本质上是带输入提示的 Input 组件，核心能力是 `辅助输入`

## 如何使用

-   Select 优先使用 `value` 作为渲染的菜单项的 `key` 值，所以 `value` 不能重复，否则无法渲染下拉菜单。如果没有设置 `key` 则会使用默认的序列 `index` 作为 `key` 值，确保这些值不会发生重复。
-   `value` 使用字符串类型，不允许出现 `null/undefined/object/array` 类型数值
-   Select 同时支持 `children` 和 `dataSource` 作为数据源，如果同时设置，则以 children 为准。
-   自定义弹出层一定要透传 `props`，参考下方示例的 `弹层定制`（因为 Overlay 的弹层的动画是依靠 `className` 实现的，如果不透传 props 则会造成无法监听到动画播放结束的事件。）

## API

### Select

| 参数                   | 说明                                                                                                                                                                                                    | 类型                                                                                                                             | 默认值                                | 是否必填 | 支持版本 |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- | -------- | -------- |
| size                   | 选择器尺寸                                                                                                                                                                                              | 'small' \| 'medium' \| 'large'                                                                                                   | 'medium'                              |          | -        |
| children               | 子元素，详细使用方法参考 demo                                                                                                                                                                           | React.ReactNode                                                                                                                  | -                                     |          | -        |
| name                   | name                                                                                                                                                                                                    | string                                                                                                                           | -                                     |          | -        |
| value                  | 当前值，用于受控模式                                                                                                                                                                                    | DataSourceItem \| DataSourceItem[]                                                                                               | -                                     |          | -        |
| defaultValue           | 初始的默认值                                                                                                                                                                                            | DataSourceItem \| DataSourceItem[]                                                                                               | -                                     |          | -        |
| placeholder            | 没有值的时候的占位符                                                                                                                                                                                    | string                                                                                                                           | -                                     |          | -        |
| autoWidth              | 下拉菜单的宽度是否与选择器保持统一                                                                                                                                                                      | boolean                                                                                                                          | true                                  |          | -        |
| label                  | 自定义内联 label                                                                                                                                                                                        | React.ReactNode                                                                                                                  | -                                     |          | -        |
| hasClear               | 是否有清除按钮（单选模式有效）                                                                                                                                                                          | boolean                                                                                                                          | -                                     |          | -        |
| state                  | 校验状态                                                                                                                                                                                                | 'error' \| 'loading' \| 'success' \| 'warning'                                                                                   | -                                     |          | -        |
| readOnly               | 是否只读，只读模式下可以展开弹层但不能选                                                                                                                                                                | boolean                                                                                                                          | -                                     |          | -        |
| disabled               | 是否禁用选择器                                                                                                                                                                                          | boolean                                                                                                                          | -                                     |          | -        |
| visible                | 当前弹层是否显示                                                                                                                                                                                        | boolean                                                                                                                          | -                                     |          | -        |
| defaultVisible         | 弹层初始化是否显示                                                                                                                                                                                      | boolean                                                                                                                          | -                                     |          | -        |
| onVisibleChange        | 弹层显示或隐藏时触发的回调                                                                                                                                                                              | (visible: boolean, type?: VisibleChangeType) => void                                                                             | -                                     |          | -        |
| popupContainer         | 弹层挂载的容器节点                                                                                                                                                                                      | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement)                                                                  | -                                     |          | -        |
| popupClassName         | 弹层的 className                                                                                                                                                                                        | string                                                                                                                           | -                                     |          | -        |
| popupStyle             | 弹层的内联样式                                                                                                                                                                                          | React.CSSProperties                                                                                                              | -                                     |          | -        |
| popupProps             | 添加到弹层上的属性                                                                                                                                                                                      | React.ComponentPropsWithRef\<typeof Popup>                                                                                       | -                                     |          | -        |
| followTrigger          | 是否跟随 trigger 滚动                                                                                                                                                                                   | boolean                                                                                                                          | -                                     |          | -        |
| popupContent           | 自定义弹层的内容                                                                                                                                                                                        | React.ReactNode                                                                                                                  | -                                     |          | -        |
| menuProps              | 弹层菜单属性                                                                                                                                                                                            | MenuProps                                                                                                                        | -                                     |          | 1.18     |
| filterLocal            | 是否使用本地过滤，在数据源为远程的时候需要关闭此项                                                                                                                                                      | boolean                                                                                                                          | true                                  |          | -        |
| filter                 | 本地过滤方法，返回一个 Boolean 值确定是否保留<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 搜索关键字<br/>_item_: 渲染节点的 item                                                                        | (key: string \| number, item: ObjectItem) => boolean                                                                             | -                                     |          | -        |
| onToggleHighlightItem  | 键盘上下键切换菜单高亮选项的回调                                                                                                                                                                        | (<br/> highlightKey?: string \| boolean \| NormalizedObjectItem \| null,<br/> type?: HighlightChangeType<br/> ) => void          | -                                     |          | -        |
| useVirtual             | 是否开启虚拟滚动模式                                                                                                                                                                                    | boolean                                                                                                                          | -                                     |          | -        |
| dataSource             | 传入的数据源，可以动态渲染子项                                                                                                                                                                          | Array\<DataSourceItem>                                                                                                           | -                                     |          | -        |
| itemRender             | 渲染 MenuItem 内容的方法<br/><br/>**签名**:<br/>**参数**:<br/>_item_: 渲染节点的 item<br/>_searchValue_: 搜索关键字（如果开启搜索）                                                                     | (item: ObjectItem, searchValue: string \| undefined) => React.ReactNode                                                          | -                                     |          | -        |
| mode                   | 选择器模式                                                                                                                                                                                              | 'single' \| 'multiple' \| 'tag'                                                                                                  | 'single'                              |          | -        |
| notFoundContent        | 弹层内容为空的文案                                                                                                                                                                                      | React.ReactNode                                                                                                                  | -                                     |          | -        |
| onChange               | Select 发生改变时触发的回调<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 选中的值<br/>_actionType_: 触发的方式，'itemClick', 'enter', 'tag'<br/>_item_: 选中的值的对象数据 (useDetailValue=false 有效) | (<br/> value: DataSourceItem \| DataSourceItem[],<br/> actionType: string,<br/> item?: ObjectItem \| ObjectItem[]<br/> ) => void | -                                     |          | -        |
| hasBorder              | 是否有边框                                                                                                                                                                                              | boolean                                                                                                                          | -                                     |          | -        |
| hasArrow               | 是否有下拉箭头                                                                                                                                                                                          | boolean                                                                                                                          | true                                  |          | -        |
| showSearch             | 展开后是否能搜索（tag 模式下固定为 true）                                                                                                                                                               | boolean                                                                                                                          | false                                 |          | -        |
| autoClearSearchValue   | 是否在选中项后清空搜索框，只在 mode 为 multiple 或 tags 时有效                                                                                                                                          | boolean                                                                                                                          | true                                  |          | -        |
| onSearch               | 当搜索框值变化时回调                                                                                                                                                                                    | (value: string, e: React.ChangeEvent\<HTMLInputElement>) => void                                                                 | -                                     |          | -        |
| onSearchClear          | 当搜索框值被清空时候的回调                                                                                                                                                                              | (actionType?: string) => void                                                                                                    | -                                     |          | -        |
| hasSelectAll           | 多选模式下是否有全选功能                                                                                                                                                                                | boolean \| string                                                                                                                | -                                     |          | -        |
| fillProps              | 填充到选择框里的值的 key                                                                                                                                                                                | string                                                                                                                           | -                                     |          | -        |
| useDetailValue         | onChange 返回的 value 使用 dataSource 的对象                                                                                                                                                            | boolean                                                                                                                          | -                                     |          | -        |
| cacheValue             | dataSource 变化的时是否保留已选的内容                                                                                                                                                                   | boolean                                                                                                                          | true                                  |          | -        |
| valueRender            | 自定义渲染 Select 选中值的效果                                                                                                                                                                          | (item: ObjectItem, props?: SelectProps) => React.ReactNode                                                                       | item =\> `item.label \|\| item.value` |          | -        |
| searchValue            | 受控搜索值，一般不需要设置                                                                                                                                                                              | string                                                                                                                           | -                                     |          | -        |
| tagInline              | 是否一行显示，仅在 mode 为 multiple 的时候生效                                                                                                                                                          | boolean                                                                                                                          | false                                 |          | -        |
| maxTagCount            | 最多显示多少个 tag                                                                                                                                                                                      | number                                                                                                                           | -                                     |          | -        |
| adjustTagSize          | tag 尺寸是否和 select 尺寸保持一致，仅在 multiple/tag 模式下有用                                                                                                                                        | boolean                                                                                                                          | false                                 |          | 1.24     |
| maxTagPlaceholder      | 隐藏多余 tag 时显示的内容，在 maxTagCount 生效时起作用<br/><br/>**签名**:<br/>**参数**:<br/>_selectedValues_: 当前已选中的元素<br/>_totalValues_: 总待选元素                                            | (<br/> selectedValues: ObjectItem[],<br/> totalValues: ObjectItem[]<br/> ) => React.ReactNode \| HTMLElement                     | -                                     |          | -        |
| hiddenSelected         | 选择后是否立即隐藏菜单 (mode=multiple/tag 模式生效)                                                                                                                                                     | boolean                                                                                                                          | -                                     |          | -        |
| showDataSourceChildren | 是否展示 dataSource 中 children                                                                                                                                                                         | boolean                                                                                                                          | true                                  |          | -        |
| onRemove               | tag 删除回调                                                                                                                                                                                            | (item: ObjectItem) => void                                                                                                       | -                                     |          | -        |
| onFocus                | Select 获得焦点时的回调                                                                                                                                                                                 | (e: React.FocusEvent\<HTMLInputElement>) => void                                                                                 | -                                     |          | -        |
| onBlur                 | Select 失去焦点时的回调                                                                                                                                                                                 | (e: React.FocusEvent\<HTMLInputElement>) => void                                                                                 | -                                     |          | -        |
| onKeyDown              | Select 触发键盘事件时的回调                                                                                                                                                                             | (e: React.KeyboardEvent\<HTMLElement>) => void                                                                                   | -                                     |          | -        |
| isPreview              | 是否为预览态                                                                                                                                                                                            | boolean                                                                                                                          | -                                     |          | -        |
| renderPreview          | 渲染预览态的内容<br/><br/>**签名**:<br/>**参数**:<br/>_values_: 选中的值<br/>_props_: 当前的属性                                                                                                        | (<br/> values: DataSourceItem \| DataSourceItem[],<br/> props?: SelectProps<br/> ) => React.ReactNode                            | -                                     |          | -        |
| autoHighlightFirstItem | 自动高亮第一个选项                                                                                                                                                                                      | boolean                                                                                                                          | true                                  |          | -        |
| highlightKey           | 高亮 key                                                                                                                                                                                                | string                                                                                                                           | -                                     |          | -        |
| defaultHighlightKey    | 默认高亮 key                                                                                                                                                                                            | string \| null                                                                                                                   | -                                     |          | -        |
| popupAutoFocus         | 展开下拉菜单时是否自动焦点到弹层                                                                                                                                                                        | boolean                                                                                                                          | false                                 |          | -        |
| popupComponent         | 渲染弹层使用的组件                                                                                                                                                                                      | React.FunctionComponent \| React.ComponentClass \| string                                                                        | -                                     |          | -        |
| tagClosable            | 是否可以关闭 tag                                                                                                                                                                                        | boolean                                                                                                                          | true                                  |          | 1.20     |

### Select.AutoComplete

| 参数                   | 说明                                               | 类型                                                                                                                    | 默认值   | 是否必填 |
| ---------------------- | -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | -------- | -------- |
| size                   | 选择器尺寸                                         | 'small' \| 'medium' \| 'large'                                                                                          | 'medium' |          |
| value                  | 当前值，用于受控模式                               | string \| number \| null                                                                                                | -        |          |
| defaultValue           | 初始化的默认值                                     | string \| number                                                                                                        | -        |          |
| placeholder            | 没有值的时候的占位符                               | string                                                                                                                  | -        |          |
| autoWidth              | 下拉菜单的宽度是否与选择器保持统一                 | boolean                                                                                                                 | true     |          |
| label                  | 自定义内联 label                                   | React.ReactNode                                                                                                         | -        |          |
| hasClear               | 是否有清除按钮（单选模式有效）                     | boolean                                                                                                                 | -        |          |
| state                  | 校验状态                                           | 'error' \| 'loading' \| 'success' \| 'warning'                                                                          | -        |          |
| readOnly               | 是否只读，只读模式下可以展开弹层但不能选           | boolean                                                                                                                 | -        |          |
| disabled               | 是否禁用选择器                                     | boolean                                                                                                                 | -        |          |
| visible                | 当前弹层是否显示                                   | boolean                                                                                                                 | -        |          |
| defaultVisible         | 弹层初始化是否显示                                 | boolean                                                                                                                 | -        |          |
| onVisibleChange        | 弹层显示或隐藏时触发的回调                         | (visible: boolean, type?: VisibleChangeType) => void                                                                    | -        |          |
| popupContainer         | 弹层挂载的容器节点                                 | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement)                                                         | -        |          |
| popupClassName         | 弹层的 className                                   | string                                                                                                                  | -        |          |
| popupStyle             | 弹层的内联样式                                     | React.CSSProperties                                                                                                     | -        |          |
| popupProps             | 添加到弹层上的属性                                 | React.ComponentPropsWithRef\<typeof Popup>                                                                              | -        |          |
| popupContent           | 自定义弹层的内容                                   | React.ReactNode                                                                                                         | -        |          |
| followTrigger          | 是否跟随 trigger 滚动                              | boolean                                                                                                                 | -        |          |
| filterLocal            | 是否使用本地过滤，在数据源为远程的时候需要关闭此项 | boolean                                                                                                                 | true     |          |
| filter                 | 本地过滤方法，返回一个 Boolean 值确定是否保留      | (key: string \| number, item: ObjectItem) => boolean                                                                    | -        |          |
| onToggleHighlightItem  | 键盘上下键切换菜单高亮选项的回调                   | (<br/> highlightKey?: string \| boolean \| NormalizedObjectItem \| null,<br/> type?: HighlightChangeType<br/> ) => void | -        |          |
| useVirtual             | 是否开启虚拟滚动模式                               | boolean                                                                                                                 | -        |          |
| dataSource             | 传入的数据源，可以动态渲染子项                     | Array\<DataSourceItem>                                                                                                  | -        |          |
| itemRender             | 渲染 MenuItem 内容的方法                           | (item: ObjectItem) => React.ReactNode                                                                                   | -        |          |
| onChange               | AutoComplete 发生改变时触发的回调                  | (value: string, actionType: string, item?: ObjectItem) => void                                                          | -        |          |
| onKeyDown              | -                                                  | (e: React.KeyboardEvent\<HTMLElement>) => void                                                                          | -        |          |
| fillProps              | 填充到选择框里的值的 key                           | string                                                                                                                  | 'value'  |          |
| autoHighlightFirstItem | 自动高亮第一个选项                                 | boolean                                                                                                                 | true     |          |
| highlightKey           | 高亮 key                                           | string                                                                                                                  | -        |          |
| defaultHighlightKey    | 默认高亮 key                                       | string                                                                                                                  | -        |          |
| onFocus                | AutoComplete 获得焦点时的回调                      | InputProps['onFocus']                                                                                                   | -        |          |
| children               | 子元素，详细使用方法参考 demo                      | React.ReactNode                                                                                                         | -        |          |
| highlightHolder        | 是否将当前高亮的选项作为 placeholder               | boolean                                                                                                                 | -        |          |

### Select.OptionGroup

| 参数  | 说明           | 类型            | 默认值 | 是否必填 |
| ----- | -------------- | --------------- | ------ | -------- |
| label | 设置分组的文案 | React.ReactNode | -      |          |

### Select.Option

| 参数     | 说明                          | 类型                                             | 默认值 | 是否必填 |
| -------- | ----------------------------- | ------------------------------------------------ | ------ | -------- |
| value    | 选项值                        | string \| number \| boolean \| null \| undefined | -      |          |
| key      | 选项值，优先级低于 value      | React.Key                                        | -      |          |
| disabled | 是否禁用                      | boolean                                          | -      |          |
| label    | 选项标签，优先级高于 children | React.ReactNode                                  | -      |          |
| children | 选项标签                      | React.ReactNode                                  | -      |          |

### ObjectItem

| 参数     | 说明                     | 类型                                             | 默认值 | 是否必填 |
| -------- | ------------------------ | ------------------------------------------------ | ------ | -------- |
| value    | 选项值                   | string \| number \| boolean \| null \| undefined | -      |          |
| label    | 选项标签                 | React.ReactNode                                  | -      |          |
| color    | 选项背景色，可选值同 Tag | TagProps['color']                                | -      |          |
| disabled | 选项是否禁用             | boolean                                          | -      |          |
| children | 子选项                   | DataSourceItem[]                                 | -      |          |
| title    | 选项标题                 | string \| null                                   | -      |          |

### DataSourceItem

```typescript
export type DataSourceItem = ObjectItem | string | boolean | number | null | undefined;
```

### VisibleChangeType

```typescript
export type VisibleChangeType =
    | 'itemClick'
    | 'enter'
    | 'esc'
    | 'keyDown'
    | 'selectAll'
    | 'update'
    | 'change'
    | 'tag';
```

### HighlightChangeType

```typescript
export type HighlightChangeType = 'up' | 'down' | 'autoFirstItem' | 'highlightKeyToNull';
```

## Select/AutoComplete 内部函数 (通过 refs 获取)

| 参数  | 说明                                                                                                                                             | 类型     | 默认值 |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------- | ------ |
| focus | 获取焦点<br><br>**签名**:<br> Function(start:Number, end: Number)<br>**参数**:<br>_start_: {Number} 光标起始位置<br>_end_: {Number} 选择结束位置 | Function |        |

## 无障碍键盘操作指南

| 按键       | 说明                 |
| :--------- | :------------------- |
| Up Arrow   | 获取当前项前一项焦点 |
| Down Arrow | 获取当前项后一项焦点 |
| Enter      | 打开列表或选择当前项 |
| Esc        | 关闭列表             |


---


## shell

# zh-CN order=0

# 基本

基本的Shell

# en-US order=0

# Type

Basic usage of shell


---


## shell

# zh-CN order=3

# 复合类型

全集

# en-US order=3

# Type

With all components.


---


## shell

# zh-CN order=1

# 头-侧边栏

头部加侧边栏，最通用的布局

# en-US order=1

# Type

Header with asider.


---


## shell

# zh-CN order=2

# 头-双侧边栏

头部加双侧边栏

# en-US order=2

# Type

Header with double asider


---


## shell

# Shell

-   category: Components
-   family: General
-   chinese: 框架
-   type: 布局

---

框架组件，仅支持IE10+。

## 何时使用

-   Shell 是整个应用的基础结构框架。
-   它体现应用的结构形式和承载应用的基本能力，让用户可以在同一套框架下完成自己所有的操作。

## 如何使用

-   Shell 应该根据业务实际诉求的复杂度进行配置；
-   同一个应用统一使用一套 Shell 框架，避免出现混乱问题。

## API

### Shell

| 参数        | 说明                                                                             | 类型                             | 默认值    | 是否必填 |
| ----------- | -------------------------------------------------------------------------------- | -------------------------------- | --------- | -------- |
| device      | 预设屏幕宽度，会影响 `Navigation`、`LocalNavigation`、`Ancillary` 等是否占据空间 | 'tablet' \| 'desktop' \| 'phone' | 'desktop' |          |
| type        | 样式类型，分浅色主题、深色主题、主题色主题                                       | 'light' \| 'dark' \| 'brand'     | 'light'   |          |
| fixedHeader | 是否固定Header，采用sticky布局，不支持 IE11                                      | boolean                          | false     |          |

### Shell.Navigation

| 参数             | 说明                                                               | 类型                          | 默认值    | 是否必填 |
| ---------------- | ------------------------------------------------------------------ | ----------------------------- | --------- | -------- |
| direction        | 方向                                                               | 'hoz' \| 'ver'                | 'hoz'     |          |
| collapse         | 是否折叠(折叠成只有icon状态)                                       | boolean                       | false     |          |
| align            | 横向模式下，导航排布的位置                                         | 'left' \| 'right' \| 'center' | 'right'   |          |
| onCollapseChange | 默认按钮触发的展开收起状态                                         | (collapse?: boolean) => void  | func.noop |          |
| trigger          | 菜单展开、收起的触发元素，默认在左上角，不想要可以设置 null 来去掉 | ReactNode                     | -         |          |
| fixed            | 是否固定，且需要在在 Shell fixedHeader时生效                       | boolean                       | false     |          |

### Shell.LocalNavigation

| 参数             | 说明                       | 类型                         | 默认值    | 是否必填 |
| ---------------- | -------------------------- | ---------------------------- | --------- | -------- |
| collapse         | 是否折叠（完全收起）       | boolean                      | false     |          |
| onCollapseChange | 默认按钮触发的展开收起状态 | (collapse?: boolean) => void | func.noop |          |

### Shell.ToolDock

| 参数             | 说明                                          | 类型                         | 默认值    | 是否必填 |
| ---------------- | --------------------------------------------- | ---------------------------- | --------- | -------- |
| collapse         | 是否折叠（完全收起）                          | boolean                      | false     |          |
| onCollapseChange | 默认按钮触发的展开收起状态                    | (collapse?: boolean) => void | func.noop |          |
| fixed            | 是否固定，且需要在在 Shell fixedHeader 时生效 | boolean                      | false     |          |

### Shell.Ancillary

| 参数             | 说明                       | 类型                         | 默认值    | 是否必填 |
| ---------------- | -------------------------- | ---------------------------- | --------- | -------- |
| collapse         | 是否折叠（完全收起）       | boolean                      | false     |          |
| onCollapseChange | 默认按钮触发的展开收起状态 | (collapse?: boolean) => void | func.noop |          |

## FAQ

### 有侧边栏的情况下，如何去掉左上角的side bar 展开、收起触发器？

设置 `<Shell.Navigation trigger={null}/>`

```jsx
<Shell>
    <Shell.Branding />
    <Shell.Navigation />
    <Shell.Action />

    <Shell.MultiTask />
    <Shell.LocalNavigation />

    <Shell.AppBar />
    <Shell.Content />
    <Shell.Footer />

    <Shell.Ancillary />
    <Shell.ToolDock>
        <Shell.ToolDockItem />
    </Shell.ToolDock>
</Shell>
```

其中 `<Shell.Content />` 采用Grid布局， 其他均为 Flex布局。


---


## slider

# zh-CN order=8

# 导航箭头位置

轮播组件的导航按钮在默认情况下为内置模式。在多图同时导航的情况下，如果想要使用外置按钮，
可以通过指定`arrowPosition`的属性值为`outer`，使用外置按钮，其默认值为`inner`。

# en-US order=8

# Navigation Arrow Position

The carousel navigation buttons are inner by default. In the case of simultaneous navigation of multiple maps, if you want to use an external button,
You can use the external button by specifying the attribute value of `arrowPosition` as `outer`. The default value is `inner`.


---


## slider

# zh-CN order=9

# 自动播放

可以通过 `autoplay` 和 `autoplaySpeed` 属性来设置组件是否自动轮播 和 自动轮播的速度。

# en-US order=9

# Autoplay

You can use the `autoplay` and `autoplaySpeed` attributes to set whether the component will automatically rotate and auto rotate.


---


## slider

# zh-CN order=0

# 基本

轮播组件共有两种类型：单图轮播和多图同时轮播。
在默认模式下（不指定任何属性值），轮播组件为单图轮播模式。

**注意：** 如果出现图片 1px 高度的问题，建议将图片的外部包括一层 `div` 来避免这个问题。

# en-US order=0

# Basic Usage

There are two types of Slider components: single picture slider and multi-picture carousel.
In the default mode (without specifying any attribute value), the carousel component is a single picture carousel mode.

**Note: ** If there is a 1px image height problem, try wrapping a `div` tag outside the `img` tag.


---


## slider

# zh-CN order=3

# 导航按钮尺寸

可以通过`arrowSize`属性来更改导航组件的按钮尺寸，默认值为`normal`，
对特定场景，比如展示的图片较大的情况下，可以选择`large`，将导航按钮设置为大按钮。

# en-US order=3

# Navigation Button Size

You can use the `arrowSize` property to change the button size of the navigation component. The default value is `normal`.
For a specific scenario, such as when the displayed picture is large, you can select `large` and set the navigation button to a large button.


---


## slider

# zh-CN order=13

# 居中模式

居中模式可以突出显示最核心区域的内容，您可以通过设置 `centerMode` 属性址为 `true` 开启该功能。

# en-US order=13

# Centering Mode

The centering mode highlights the content of the most core area. You can enable this function by setting the `centerMode` property address to `true`.


---


## slider

# zh-CN order=7

# 自定义导航箭头

开发者可以通过 `prevArrow` 和 `nextArrow` 两个属性传入自定义的导航箭头组件。

# en-US order=7

# Custom Navigation Arrows

You can pass custom navigation arrow components through the two attributes `prevArrow` and `nextArrow`.


---


## slider

# zh-CN order=16

# 使用自定义组件

你可以为传递自定义组件到 Slider 组件中。前提是该组件一定要开放透传 props 到下层组件或元素，Slider 底层需要执行元素的 clone 操作。

# en-US order=16

# Use Custom Components in Slider

You can pass custom components to the Slider component. The premise is that the component must open transparently props to the underlying component or element, and the Slider needs to perform the clone operation of the element.


---


## slider

# zh-CN order=4

# 导航锚点方向

通过 `dotsDirection` 可以改变导航锚点的位置，默认为 `hoz` 即水平方向。
当其值设为 `ver` 时为垂直方向展示。

# en-US order=4

# Navigation Anchor Direction

The direction of the navigation anchor can be changed via `dotsDirection`. The default is `hoz`, which is the horizontal direction.The vertical direction is displayed when the value is set to `ver`.


---


## slider

# zh-CN order=6

# 自定义导航锚点

通过 `dotsRender` 可以自定义修改 dots，通过 `dotsClass` 可覆盖 dots 的样式。

# en-US order=6

# Custom Navigation Anchor

`dotsRender` can be used to modify dost, and `dotsClass` can override dots.


---


## slider

# zh-CN order=5

# 导航锚点触发方式

通过 `triggerType` 可以定义dots触发方式，共有两种触发方式：['click', 'hover'];
当其值设为 `hover` 时为鼠标经过触发滚动。

# en-US order=5

# Navigation Anchor Trigger

The trigger mode can be defined by `triggerType`. There are two trigger modes: ['click', 'hover'];
When the value is set to `hover`, the mouse rolls over the trigger.


---


## slider

# zh-CN order=18

# Fade

切换跑马灯时使用渐变效果。

# en-US order=18

# Fade

Use a fade effect when switching between marquees.


---


## slider

# zh-CN order=10

# 禁止循环

默认情况下，轮播组件的表现为无穷循环模式。如果你不想无穷循环，
可以通过设置 `infinite` 为 `false`，用来禁止循环模式。

值得注意的是，由于组件的默认行为是无穷模式，所以默认情况下，自动将单张图片复制了两份，
如果你不想启用这样的复制效果，只要关闭 `infinite` 属性即可。

# en-US order=10

# No Loop

By default, the Slider component behaves in an endless loop mode. If you don't want endless loops,
You can disable the loop mode by setting `infinite` to `false`.

It is worth noting that since the default behavior of the component is the infinite mode, by default, the single image is automatically duplicated.
If you do not want to enable such a copy effect, just close the ʻinfinite` attribute.


---


## slider

# zh-CN order=1

# 多图轮播

在单图轮播的基础上，通过指定`slidesToShow`属性值，可以同时进行多图轮播。
可以通过 `slidesToScroll` 属性制定单次轮播图片的个数。

# en-US order=1

# Multiple Picture

On the basis of the single-image carousel, multiple map carousels can be performed at the same time by specifying the `slidesToShow` attribute value.
You can set the number of single-rotation pictures with the `slidesToScroll` attribute.


---


## slider

# zh-CN order=11

# 悬浮时暂停

可以通过设置 `pauseOnHover` 属性为 `true` 使得 Slide 在鼠标悬浮时自动停止轮播。

# en-US order=11

# Pause When Mouse Is Floating

You can make Slide to automatically stop the carousel when the mouse is hovering by setting the `pauseOnHover` property to `true`.


---


## slider

# zh-CN order=14

# ActiveIndex

通过 `index` 属性可以快速的定位到指定次序的 slider 。

# en-US order=14

# ActiveIndex

With the `index` attribute you can quickly navigate to the specified sequence of sliders.


---


## slider

# zh-CN order=19

# onChange 钩子

你可以利用 `onChange` 钩子函数处理一些额外的逻辑。

# en-US order=19

# onChange

You can use the `onChange` hook function to handle some extra logic.


---


## slider

# zh-CN order=2

# 垂直滑动

轮播组件可以通过 `slideDirection` 属性设置两种轮播方向。当值为 `ver` 时轮播方向为垂直方向，
默认为值为 `hoz` 。垂直模式也可以设置单图和多图轮播。

# en-US order=2

# Swipe Vertically

The slider component can set two carousel directions with the `slideDirection` attribute. When the value is `ver`, the carousel direction is vertical. The default value is `hoz`. Vertical mode can also set single map and multi picture rotation.


---


## slider

# zh-CN order=17

# 弹出来的跑马灯

如果你要将 Slider 放到 Dialog 中，此时你需要关闭 Dialog 的动画，避免 Slider 在计算内部元素宽度时造成出错。

# en-US order=17

# Slider in Dialog

If you want to put the Slider in the Dialog, you need to close the Dialog animation at this time, to avoid the Slider causing an error when calculating the inner element width.


---


## slider

# zh-CN order=12

# 外部控制

用户可以包装 Slider 组件，以便进行外部控制。例如通过包装组件实现外部对 Slider 组件 `autoplay` 和 `autoplaySpeed` 值的控制。

# en-US order=12

# Controled Swiping

Users can package Slider components for controled. For example, To control of Slider components `autoplay` and `autoplaySpeed` values is achieved through a wrapper component.


---


## slider

# zh-CN order=15

# 不同的图片宽度

Slider 在默认情况下会认为所有的子元素是等宽的。
通过设置 `variableWidth` 为 `true`，您可以在 Slider 中放置不同宽度的图片。

# en-US order=15

# Different Picture Widths

By default, Slider considers all child elements to be equal.
By setting `variableWidth` to `true`, you can place images of different widths in the Slider.


---


## slider

# Slider

-   category: Components
-   family: DataDisplay
-   chinese: 图片轮播
-   type: 展示

---

轮播组件，就是以幻灯片的方式，在页面中横向展示诸多内容的组件。

## 何时使用

-   轮播内容相互独立，前后在内容以及数据上都不存在逻辑关系。
-   **单图轮播**：该样式通常用于承载运营banner，是一个位置相对固定的模块。
-   **多图轮播**：单元信息浏览

## 如何使用

1.  当轮播组件中只有一张图片的时候，轮播组件会隐藏导航锚点、禁止自动循环（即使上层设置了）、禁止拖拽播放（即使上层设置了）。
2.  如果您要将 Slider 放到 Dialog 中，此时你需要关闭 Dialog 的动画，避免 Slider 在计算内部元素宽度时造成出错。
3.  如果出现图片高度 1px 的问题，可以尝试在 `img` 标签的外部包裹一层 `div` 标签。

## API

### Slider

| 参数               | 说明                                                                                                                      | 类型                                                                        | 默认值   | 是否必填 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | -------- | -------- |
| className          | 自定义传入的样式                                                                                                          | string                                                                      | -        |          |
| adaptiveHeight     | 是否使用自适应高度                                                                                                        | boolean                                                                     | false    |          |
| animation          | 动效类型，默认是'slide'                                                                                                   | string \| boolean                                                           | 'slide'  |          |
| arrows             | 是否显示箭头                                                                                                              | boolean                                                                     | true     |          |
| arrowSize          | 导航箭头大小                                                                                                              | 'medium' \| 'large'                                                         | 'medium' |          |
| arrowPosition      | 导航箭头位置                                                                                                              | 'inner' \| 'outer'                                                          | 'inner'  |          |
| arrowDirection     | 导航箭头方向                                                                                                              | 'hoz' \| 'ver'                                                              | 'hoz'    |          |
| autoplay           | 是否自动播放                                                                                                              | boolean                                                                     | false    |          |
| autoplaySpeed      | 自动播放的速度                                                                                                            | number                                                                      | 3000     |          |
| prevArrow          | 前向箭头节点                                                                                                              | ReactElement                                                                | -        |          |
| nextArrow          | 后向箭头节点                                                                                                              | ReactElement                                                                | -        |          |
| centerMode         | 是否启用居中模式                                                                                                          | boolean                                                                     | false    |          |
| dots               | 是否显示导航锚点                                                                                                          | boolean                                                                     | true     |          |
| dotsDirection      | 导航锚点方向                                                                                                              | 'hoz' \| 'ver'                                                              | 'hoz'    |          |
| dotsRender         | 自定义导航锚点<br/><br/>**签名**:<br/>**参数**:<br/>_index_: 锚点编号<br/>_current_: 当前幻灯片编号                       | (index: number, current: number) => void                                    | -        |          |
| draggable          | 是否可拖拽                                                                                                                | boolean                                                                     | true     |          |
| infinite           | 是否使用无穷循环模式                                                                                                      | boolean                                                                     | true     |          |
| defaultActiveIndex | 初始被激活的轮播图                                                                                                        | number                                                                      | 0        |          |
| lazyLoad           | 是否启用懒加载                                                                                                            | boolean                                                                     | false    |          |
| slideDirection     | 轮播方向                                                                                                                  | 'hoz' \| 'ver'                                                              | 'hoz'    |          |
| slidesToShow       | 同时展示的图片数量                                                                                                        | number                                                                      | 1        |          |
| slidesToScroll     | 同时滑动的图片数量                                                                                                        | number                                                                      | 1        |          |
| speed              | 轮播速度                                                                                                                  | number                                                                      | 600      |          |
| activeIndex        | 跳转到指定的轮播图（受控）                                                                                                | number                                                                      | -        |          |
| triggerType        | 导航锚点触发方式                                                                                                          | 'click' \| 'hover'                                                          | 'click'  |          |
| onChange           | 轮播切换的回调函数                                                                                                        | (index: number) => void                                                     | -        |          |
| centerPadding      | center 模式下的边缘 padding 值 (px or %);                                                                                 | string                                                                      | '50px'   |          |
| cssEase            | CSS3 Animation Easing，默认‘ease’                                                                                         | string                                                                      | 'ease'   |          |
| focusOnSelect      | 多图轮播时，是否在点击选中后自动居中                                                                                      | boolean                                                                     | 'false'  |          |
| style              | 自定义样式                                                                                                                | CSSProperties                                                               | -        |          |
| waitForAnimate     | 是否等待动画结束后再执行动作                                                                                              | boolean                                                                     | true     |          |
| accessibility      | 是否启用无障碍支持，使用左右键可以切换轮播图                                                                              | boolean                                                                     | false    |          |
| children           | 子元素                                                                                                                    | ReactNode                                                                   | -        |          |
| dotsClass          | 导航锚点样式类名                                                                                                          | string                                                                      | -        |          |
| variableWidth      | Slider 在默认情况下会认为所有的子元素是等宽的。通过设置 `variableWidth` 为 `true`，您可以在 Slider 中放置不同宽度的图片。 | boolean                                                                     | -        |          |
| onBeforeChange     | 轮播切换前的回调函数                                                                                                      | (index: number, currentIndex?: number) => void                              | -        |          |
| swipe              | 是否启用滑动                                                                                                              | boolean                                                                     | true     |          |
| edgeEvent          | 在滑动到头时触发的回调函数                                                                                                | (swipeDirection: 'left' \| 'right') => void                                 | -        |          |
| edgeFriction       | 边缘摩擦系数，数值越大，滑动越慢                                                                                          | number                                                                      | 0.35     |          |
| swipeEvent         | 滑动事件回调函数                                                                                                          | (swipeDirection: 'left' \| 'right' \| 'vertical' \| 'down' \| 'up') => void | -        |          |
| pauseOnHover       | 在鼠标悬浮时自动停止轮播                                                                                                  | boolean                                                                     | false    |          |

## 说明

next-slider is forked from [react-slick](https://github.com/akiran/react-slick).


---


## split-button

# zh-CN order=4

# 无障碍支持

为了使得屏幕阅读器能传达右侧按钮的含义，我们可以通过`triggerProps`传递对右侧按钮的`aria-label`描述。

# en-US order=4

# Accessibility

To make screen-reader understand the meaning of the button on the right, we can pass description of `aria-label` via `triggerProps` to `SplitButton` component. Please refer to `ARIA and KeyBoard` for keyboard operation information.


---


## split-button

# zh-CN order=0

# 基本

最简单的用法。支持 `Button` 的 `type`, `size`, `component`, `ghost` 等属性透传。

# en-US order=0

# Basic

Use SplitButton as Button.


---


## split-button

# zh-CN order=3

# 复合使用

复合使用菜单，监听菜单行为展示左侧操作。

# en-US order=3

# Composite

A more complex use case, control menu with attributes from Menu.


---


## split-button

# zh-CN order=3

# 复杂菜单展示

支持菜单组和菜单分割线，使用方法同 `Menu.Group`, `Menu.Item`, `Menu.Divider`。

# en-US order=3

# Menu

SplitButton with complex menus.


---


## split-button

# zh-CN order=1

# 尺寸

SplitButton 实际是上一个按钮组，通过 `size` 属性可以改变按钮组的大小。

# en-US order=1

# Size

Change the component size by passing `size`.


---


## split-button

# SplitButton

-   category: Components
-   family: General
-   chinese: 分隔按钮
-   type: 基本

---

由两部分组成的按钮，左侧触发操作，右侧触发菜单。

## 何时使用

-   `SplitButton` 由 `Button` 和 `Menu` 组成，右侧 `Icon` 按钮部分为弹层菜单的触发区域，存放多个操作，左侧按钮部分则进行操作触发；
-   推荐按钮操作多于3种时使用。

## API

### SplitButton

| 参数                  | 说明                                                                                                                                                                                                                                              | 类型        | 默认值       |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | --------- |
| size                | 按钮组的尺寸<br/><br/>**可选值**:<br/>'small', 'medium', 'large'                                                                                                                                                                                         | Enum      | 'medium'  |
| type                | 按钮的类型<br/><br/>**可选值**:<br/>'normal', 'primary', 'secondary'                                                                                                                                                                                    | Enum      | 'normal'  |
| label               | 主按钮的文案                                                                                                                                                                                                                                          | ReactNode | -         |
| component           | 设置标签类型<br/><br/>**可选值**:<br/>'button', 'a'                                                                                                                                                                                                      | Enum      | -         |
| ghost               | 是否为幽灵按钮<br/><br/>**可选值**:<br/>'light', 'dark', false, true                                                                                                                                                                                      | Enum      | -         |
| defaultSelectedKeys | 默认激活的菜单项（用法同 Menu 非受控）                                                                                                                                                                                                                          | Array     | \[]       |
| selectedKeys        | 激活的菜单项（用法同 Menu 受控）                                                                                                                                                                                                                             | Array     | -         |
| selectMode          | 菜单的选择模式<br/><br/>**可选值**:<br/>'single', 'multiple'                                                                                                                                                                                              | Enum      | -         |
| onSelect            | 选择菜单项时的回调，参考 Menu<br/><br/>**签名**:<br/>Function() => void                                                                                                                                                                                       | Function  | func.noop |
| onItemClick         | 点击菜单项时的回调，参考 Menu<br/><br/>**签名**:<br/>Function() => void                                                                                                                                                                                       | Function  | func.noop |
| triggerProps        | 触发按钮的属性（支持 Button 的所有属性透传）                                                                                                                                                                                                                      | Object    | -         |
| autoWidth           | 弹层菜单的宽度是否与按钮组一致                                                                                                                                                                                                                                 | Boolean   | true      |
| visible             | 弹层是否显示                                                                                                                                                                                                                                          | Boolean   | -         |
| defaultVisible      | 弹层默认是否显示                                                                                                                                                                                                                                        | Boolean   | -         |
| onVisibleChange     | 弹层显示状态变化时的回调函数<br/><br/>**签名**:<br/>Function(visible: Boolean, type: String) => void<br/>**参数**:<br/>_visible_: {Boolean} 弹层显示状态<br/>_type_: {String} 触发弹层显示或隐藏的来源 menuSelect 表示由menu触发； fromTrigger 表示由trigger的点击触发； docClick 表示由document的点击触发 | Function  | func.noop |
| popupTriggerType    | 弹层的触发方式<br/><br/>**可选值**:<br/>'click', 'hover'                                                                                                                                                                                                  | Enum      | 'click'   |
| popupAlign          | 弹层对齐方式, 详情见Overlay align                                                                                                                                                                                                                        | String    | -         |
| popupStyle          | 弹层自定义样式                                                                                                                                                                                                                                         | Object    | -         |
| popupClassName      | 弹层自定义样式类                                                                                                                                                                                                                                        | String    | -         |
| popupProps          | 透传给弹层的属性                                                                                                                                                                                                                                        | Object    | -         |
| popupContainer      | 弹层容器                                                                                                                                                                                                                                            | any       | -         |
| followTrigger       | 是否跟随滚动                                                                                                                                                                                                                                          | Boolean   | -         |
| menuProps           | 透传给 Menu 的属性                                                                                                                                                                                                                                    | Object    | {}        |
| leftButtonProps     | 透传给 左侧按钮 的属性                                                                                                                                                                                                                                    | Object    | {}        |


---


## step

# zh-CN order=0

# 基本用法

在最简单的情况下，Step 有三种类型，可以通过 `shape` 属性进行切换。

`circle`类型可通过`labelPlacement`设置文本排列方向。

# en-US order=0

# Basic

In the simplest case, Step has three types that can be toggled through the `shape` attribute.

The `circle` type can be used to set the orientation of the text through `labelPlacement`.


---


## step

# zh-CN order=7

# 步骤切换

通常配合内容及按钮使用，表示一个流程的处理进度。

# en-US order=6

# Switch steps

By default, Step is defined as a display component. The upper component can modify the current step by modifying the value of the current property passed in. At the same time, each node's click event can be set to customize the callback.


---


## step

# zh-CN order=5

# 步骤项自定义渲染

`Step.Item` 默认有三种状态，分别是 `wait`, `process`, `finish`。
用户可以通过传递 `itemRender` 属性进行自定义的渲染。

# en-US order=4

# Step.Item custom step node render function

`Step.Item` has three states by default, which are `wait`, `process`, `finish`.
Users can customize rendering by passing the itemRender property.


---


## step

# zh-CN order=1

# 垂直模式

对于点型和圆圈型的 Step 组件而言，可以通过设置 `direction` 属性设置其展示方向为垂直。
箭头形不支持垂直模式。

# en-US order=1

# Vertical mode

For type `dot` and `circle` Step components, you can set their orientation to vertical by setting the `direction` property.
While, type `arrows` do not support vertical mode.


---


## step

# zh-CN order=4

# 禁用步骤项

可以通过在 `Step.Item` 上设置 `disabled` 属性来禁用某个步骤。

# en-US order=3

# Disable Step

You can disable a step by setting the `disabled` attribute on `Step.Item`.


---


## step

# zh-CN order=2

# 自定义图标和百分比展示

可以在点型和圆形步骤条中使用图标，圆形步骤条还支持使用百分比。

# en-US order=2

# Icons and percentages

You can use icons in `dot` and `circle` step, and `circle` step also support percentages.


---


## step

# zh-CN order=6

# 不可点击

只读模式，不可触发回调。

# en-US order=5

# Readonly mode

In read-only mode, callbacks cannot be triggered.


---


## step

# zh-CN order=3

# 步骤运行错误

可通过自定义 step item 来实现当前步骤的状态。

# en-US order=9

# Disable Step

You can display StepItem's state by customizing the content of StepItem.


---


## step

# Step

-   category: Components
-   family: Navigation
-   chinese: 步骤
-   type: 展示

---

引导用户按照流程完成任务的导航条。

## 何时使用

当任务复杂或者存在先后关系时，将其分解成一系列步骤，从而简化任务。

## API

### Step

| 参数           | 说明                                                                                                                                                                                                                                          | 类型                                                                                                                      | 默认值   | 是否必填 |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | -------- | -------- |
| current        | 当前步骤                                                                                                                                                                                                                                      | number                                                                                                                    | 0        |          |
| shape          | 类型                                                                                                                                                                                                                                          | StepShape                                                                                                                 | 'circle' |          |
| direction      | 展示方向                                                                                                                                                                                                                                      | StepDirection                                                                                                             | 'hoz'    |          |
| labelPlacement | 横向布局时的内容排列方式                                                                                                                                                                                                                      | StepDirection                                                                                                             | 'ver'    |          |
| readOnly       | 是否只读模式                                                                                                                                                                                                                                  | boolean                                                                                                                   | -        |          |
| animation      | 是否开启动效                                                                                                                                                                                                                                  | boolean                                                                                                                   | true     |          |
| itemRender     | 自定义渲染节点<br/><br/>**签名**:<br/>**参数**:<br/>_index_: 节点索引<br/>_status_: 节点状态<br/>_title_: 节点标题，仅在 `shape='circle'` 时会传递<br/>_content_: 节点内容，仅在 `shape='circle'` 时会传递<br/>**返回值**:<br/>节点的渲染结果 | (<br/> index: number,<br/> status: StepStatus,<br/> title?: ReactNode,<br/> content?: ReactNode<br/> ) => React.ReactNode | -        |          |
| stretch        | 宽度是否横向拉伸                                                                                                                                                                                                                              | boolean                                                                                                                   | false    |          |

### Step.Item

| 参数       | 说明                                                                                                                                                                                                                                                                                | 类型                                                                                                                                  | 默认值 | 是否必填 |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------ | -------- |
| status     | 步骤的状态，如不传，会根据外层的 Step 的 current 属性生成                                                                                                                                                                                                                           | StepStatus                                                                                                                            | -      |          |
| title      | 标题                                                                                                                                                                                                                                                                                | React.ReactNode                                                                                                                       | -      |          |
| icon       | 图标                                                                                                                                                                                                                                                                                | string                                                                                                                                | -      |          |
| content    | 内容填充，shape 为 arrow 时无效                                                                                                                                                                                                                                                     | React.ReactNode                                                                                                                       | -      |          |
| itemRender | StepItem 的自定义渲染，会覆盖父节点设置的 itemRender<br/><br/>**签名**:<br/>**参数**:<br/>_index_: 节点索引<br/>_status_: 节点状态<br/>_title_: 节点标题，仅在 `shape='circle'` 时会传递<br/>_content_: 节点内容，仅在 `shape='circle'` 时会传递<br/>**返回值**:<br/>节点的渲染结果 | (<br/> index: number,<br/> status: StepStatus,<br/> title?: React.ReactNode,<br/> content?: React.ReactNode<br/> ) => React.ReactNode | -      |          |
| percent    | 百分比                                                                                                                                                                                                                                                                              | number                                                                                                                                | -      |          |
| disabled   | 是否禁用                                                                                                                                                                                                                                                                            | boolean                                                                                                                               | -      |          |
| onClick    | 点击步骤时的回调<br/><br/>**签名**:<br/>**参数**:<br/>_index_: 节点索引                                                                                                                                                                                                             | (index: number) => unknown                                                                                                            | -      |          |

### StepDirection

```typescript
export type StepDirection = 'hoz' | 'ver';
```

### StepStatus

```typescript
export type StepStatus = 'wait' | 'process' | 'finish';
```

### StepShape

```typescript
export type StepShape = 'circle' | 'arrow' | 'dot';
```

## FAQ

### 为什么设置 Step 的展示方向不生效？

`Step`组件有三种类型（shape） `shape?: 'arrow' | 'circle' | 'dot';`, 其中：

-   `shape='arrow'` 只有一种模式；
-   `shape='circle'` 有两种方向；
    -   `direction='ver'` 垂直方向
    -   `direction='hoz'` 水平方向，根据文案与图标位置的不同分为两种模式
        -   `labelPlacement='hoz'` 文案与图标 左右布局
        -   `labelPlacement='ver'` 文案与图标 上下布局
-   `shape='dot'` 有两种方向；
    -   `direction='ver'` 垂直方向
    -   `direction='hoz'` 水平方向

如果发现 step 展示方向设置不生效，可先检查是否使用了正确的 API（比如`labelPlacement`就仅在`shape='circle'` `direction='hoz'`时才生效。


---


## switch

# zh-CN order=5

# 无障碍支持

组件内部已支持无障碍，设置`aria-label`对组件进行描述。

# en-US order=5

# Accessibility

Components inside has support for accessibility, set `aria-label` on component is described.


---


## switch

# zh-CN order=0

# 简单

最简单的用法

# en-US order=0

# Basic

Basic usage.


---


## switch

# zh-CN order=3

# 文字和图标

带有文字说明和图标

# en-US order=3

# text and icon

with text or icon


---


## switch

# zh-CN order=2

# 不可用

Switch 失效状态。

# en-US order=2

# disabled

Disabled switch.


---


## switch

# zh-CN order=0

# 加载中

带加载中状态的 switch

# en-US order=0

# loading

Switch with loading


---


## switch

# zh-CN order=4

# 两种大小

size="small" 表示小号开关

# en-US order=4

# size

use size=small to set small switch


---


## switch

# Switch

-   category: Components
-   family: DataEntry
-   chinese: 开关组件
-   type: 表单

---

开关组件

## 何时使用

开/关切换器切换单个设置选项的状态。开关控制器中的选项，以及它所在的状态，应该用伴随的内联标签显示清楚。开关选择器具有和单选按钮一样的视觉属性。使用文本“开”和“关”滑动切换已经过时了。使用这里显示的开关选择器代替。

## 如何使用

对于 checkChildren 和 unCheckedChildren 的自定义要考虑文字大小，因为 switch 的宽度有限，默认一个汉字大小。如果设置成多个字或者英文要注意宽度控制。

## FAQ

1.23 版本增加了 `autoWidth` API，我们推荐用户默认开启，同时在 2.0 里也会默认设置为 true。开启后，原 `<Switch style={{display: 'block'}}>` 写法的用户可能会出现样式异常。

## API

### Switch

| 参数              | 说明                                                                                                                                                     | 类型                                                                                                                      | 默认值   | 是否必填 |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | -------- | -------- |
| defaultChecked    | 开关是否打开默认值 (非受控)                                                                                                                              | boolean                                                                                                                   | false    |          |
| checked           | 开关是否打开（受控）                                                                                                                                     | boolean                                                                                                                   | -        |          |
| onChange          | 开关状态改变时事件<br/><br/>**签名**:<br/>**参数**:<br/>_checked_: 是否打开                                                                              | (<br/> checked: boolean,<br/> e: React.MouseEvent\<HTMLDivElement> \| React.KeyboardEvent\<HTMLDivElement><br/> ) => void | -        |          |
| size              | switch 的尺寸                                                                                                                                            | 'medium' \| 'small'                                                                                                       | 'medium' |          |
| loading           | 加载状态                                                                                                                                                 | boolean                                                                                                                   | false    |          |
| disabled          | 表示开关被禁用                                                                                                                                           | boolean                                                                                                                   | false    |          |
| autoWidth         | 宽度根据内容自适应                                                                                                                                       | boolean                                                                                                                   | false    |          |
| isPreview         | 是否预览模式                                                                                                                                             | boolean                                                                                                                   | false    |          |
| renderPreview     | 自定义预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_checked_: 是否打开<br/>_props_: 组件参数对象<br/>**返回值**:<br/>预览模式下的渲染内容 | (checked: boolean, props: SwitchProps) => React.ReactNode                                                                 | -        |          |
| checkedChildren   | 打开时的内容                                                                                                                                             | React.ReactNode                                                                                                           | -        |          |
| unCheckedChildren | 关闭时的内容                                                                                                                                             | React.ReactNode                                                                                                           | -        |          |
| onClick           | 鼠标点击事件                                                                                                                                             | (e: React.MouseEvent\<HTMLDivElement> \| React.KeyboardEvent\<HTMLDivElement>) => void                                    | -        |          |
| onKeyDown         | 键盘按键事件                                                                                                                                             | (e: React.KeyboardEvent\<HTMLDivElement>) => void                                                                         | -        |          |

## 无障碍键盘操作指南

| 按键  | 说明         |
| :---- | :----------- |
| Enter | 切换选中状态 |
| SPACE | 切换选中状态 |


---


## tab

# zh-CN order=0

# 简单用法

使用 Tab 最简单的例子。

# en-US order=0

# Basic

A simple case.


---


## tab

# zh-CN order=6

# 可关闭/新增选项卡

可关闭选项卡，可以通过在 `Tab.Item` 上设置 `closeable` 属性设置该选项卡是否可关闭。可以通过 `showAdd` 开启新增功能

# en-US order=6

# Closeable

Creating closeable tabs by pass attribute `closeable` to `Tab.Item`. use `showAdd` use add


---


## tab

# zh-CN order=9

# 自定义样式

在 Tab 已有样式的基础上，可以通过 `contentStyle`, `contentClassName` 等属性自由的进行样式自定义。

# en-US order=9

# Custom style

Customize Tab style by `contentStyle`, `contentClassName`.


---


## tab

# zh-CN order=10

# 自定义选项卡

Tab 支持使用 `tabRender` 属性返回自定义组件作为选项卡内容，注意该属性接收函数作为属性值。

# en-US order=10

# Custom tab

By default, tabs are rendered by a default template function. Howerver, you can pass your template function to `tabRender`.


---


## tab

# zh-CN order=15

# 禁止键盘事件

通过 `disabledKeyboard=true` 禁止 Tab 聚焦时的键盘 `↑`,`↓`,`←` ,`→` 切换

# en-US order=15

# Disable Keyboard

disable `↑`,`↓`,`←` ,`→` keyboard event when tab is active


---


## tab

# zh-CN order=8

# 禁用

可以通过 `disabled` 属性禁用某一个选型卡。

# en-US order=8

# Disable

Disable tabs by passing `disabled` to `Tab.Item`.


---


## tab

# zh-CN order=12

# 可编辑的 Tab

Tab 允许开发者在上层进行自由的行为控制，例如用户可以基于 Tab 开发一个标题部分双击可编辑的 Tab ，
此时用户只要传入自定义组件给 TabPane 即可，Tab 可以将底层事件对象传递给用户的自定义组件。

# en-US order=12

# Editable tab

Create an editable tab.


---


## tab

# zh-CN order=5

# 超出时滑动

当 Tab 标签非常多时，组件会自动增加滑动支持 (可以左右、上下滑动)。可以用过 `excessMode` 属性切换滑动模式，该属性仅在`tabPosition`为`top`或者`bottom`时生效。

# en-US order=5

# Excess mode

If your Tab excess the range, you can setting `excessMode` to `dropdown` for vertical display, or `slide` for horizontal display, just note that this `excessMode` will only be effective when `tabPosition` is set to be `top` or `bottom`.


---


## tab

# zh-CN order=11

# 附加额外内容

通过 `extra` 属性添加附加内容，请确保只在有限选项卡的情况下才使用附加内容, 该功能在选项卡溢出时会和溢出导航的按钮冲突。

# en-US order=11

# Extra

Pass your custom contents to `extra`, please consider using this when the tab-items are limited, since it is not designed to be used in combination with excess-mode.


---


## tab

# zh-CN order=3

# 按需加载和自动卸载

默认情况 Tab 不会提前渲染好所有的内容，而是根据 Tab 的激活情况依次进行渲染。

-   可以设置 `lazyLoad={false}` 一次渲染所有 TabItem 内容。
-   可以设置 `unmountInactiveTabs` 在切换选项卡时自动卸载其他 TabItem。

# en-US order=3

# LazyLoad and AutoUnmount

Disable lazy load by setting `lazyLoad={false}`, and enable auto unmount inactive tabs by setting `unmountInactiveTabs`.


---


## tab

# zh-CN order=14

# 选项卡嵌套

可以将不同类型的选项卡进行嵌套

# en-US order=14

# Nest tabs

Nest multiple Tabs.


---


## tab

# zh-CN order=4

# 位置

包裹型选项卡支持通过 `tabPosition` 属性设置选项卡的位置，支持 `top | right | bottom | left` 四个方向。

# en-US order=4

# Positon

Change tab position by `tabPosition`, values `top | right | bottom | left`.


---


## tab

# zh-CN order=1

# 形态

根据使用场景及触发控件的类型，可以通过 `shape` 属性配置选项卡的类型，主要包括：

-   `pure` 普通选项卡（默认）
-   `wrapped` 包裹型选项卡
-   `text` 文本型选项卡
-   `capsule` 胶囊型选项卡

# en-US order=1

# Shape

Change shape of Tab by `shape`.


---


## tab

# zh-CN order=2

# 小号尺寸

可以通过 `size=small` 设置小号尺寸，一般用于弹出框等较狭窄的容器内。

# en-US order=2

# small Size

Change the Tab size by `size`.


---


## tab

# zh-CN order=13

# 在 Grid 中使用 Tab

当 Tab 位于 Grid 组件的布局中时，由于 Grid 默认使用 `flex` 布局方式，当选项卡数量过多时，会导致内层元素撑起整个 `flex` 容器，此时需要给容器添加自定义样式 `overflow: hidden`。

# en-US order=13

# Tab in Grid

Use Tab in Grid should adding `overflow: hidden` to the container.


---


## tab

# zh-CN order=7

# 触发类型

Tab 支持 `click` 切换和 `hover` 切换两种触发类型，默认为 `click` 触发，您可以使用 `triggerType` 属性修改默认的触发类型。

# en-US order=7

# Trigger type

Change default tirgger type by `triggerType`.


---


## tab

# Tab

-   category: Components
-   family: Navigation
-   chinese: 选项卡
-   type: 导航

---

选项卡切换组件。

## 何时使用

TAB 让用户可以在不同子任务、视图、模式之间切换，它具有全局导航的作用，是全局功能的主要展示和切换区域，一个TAB标记一个核心功能，TAB之间可以快速点击切换。该窗口包含2个以上的选项卡，所有选项卡可以排列在一行中，即使该用户界面被本地化后也是如此。提供平级的区域将大块内容进行收纳和展现，保持界面整洁。

Fusion 提供了三级选项卡，分别用于不同的场景。

-   普通选项卡，引领整页面的内容，起导航的作用。
-   文本型选项卡。
-   包裹型选项卡，在页面结构中，只是局部展示，需要和其他内容结合出现。
-   胶囊型选项卡。

## 如何使用

如果您不想开启动效，可以通过设置 `animation` 属性值为 `false` 来关闭。

## API

### Tab

| 参数                | 说明                                                                                                                                                                                | 类型                                                                                                            | 默认值   | 是否必填 |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- | -------- | -------- |
| activeKey           | 被激活的选项卡的 key, 赋值则 tab 为受控组件，用户无法切换                                                                                                                           | string                                                                                                          | -        |          |
| defaultActiveKey    | 初始化时被激活的选项卡的 key                                                                                                                                                        | string                                                                                                          | -        |          |
| shape               | 外观形态                                                                                                                                                                            | 'pure' \| 'wrapped' \| 'text' \| 'capsule'                                                                      | 'pure'   |          |
| animation           | 是否开启动效                                                                                                                                                                        | boolean                                                                                                         | true     |          |
| excessMode          | 选项卡过多时的滑动模式                                                                                                                                                              | 'slide' \| 'dropdown'                                                                                           | 'slide'  |          |
| tabPosition         | 导航选项卡的位置，只适用于包裹型（wrapped）选项卡                                                                                                                                   | 'top' \| 'bottom' \| 'left' \| 'right'                                                                          | 'top'    |          |
| size                | 尺寸                                                                                                                                                                                | 'small' \| 'medium'                                                                                             | 'medium' |          |
| triggerType         | 激活选项卡的触发方式                                                                                                                                                                | 'hover' \| 'click'                                                                                              | 'click'  |          |
| lazyLoad            | 是否延迟加载 TabPane 的内容，默认开启，即不提前渲染                                                                                                                                 | boolean                                                                                                         | true     |          |
| unmountInactiveTabs | 是否自动卸载未处于激活状态的选项卡                                                                                                                                                  | boolean                                                                                                         | false    |          |
| navStyle            | 导航条的自定义样式                                                                                                                                                                  | CSSProperties                                                                                                   | -        |          |
| navClassName        | 导航条的自定义样式类                                                                                                                                                                | string                                                                                                          | -        |          |
| contentStyle        | 内容区容器的自定义样式                                                                                                                                                              | CSSProperties                                                                                                   | -        |          |
| contentClassName    | 内容区容器的自定义样式类                                                                                                                                                            | string                                                                                                          | -        |          |
| extra               | 导航栏附加内容                                                                                                                                                                      | ReactNode                                                                                                       | -        |          |
| disableKeyboard     | 禁用键盘事件                                                                                                                                                                        | boolean                                                                                                         | false    |          |
| onClick             | 点击单个选项卡时触发的回调                                                                                                                                                          | (key: string) => void                                                                                           | -        |          |
| onChange            | 选项卡发生切换时的事件回调<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 改变后的 key                                                                                                 | (key: string) => void                                                                                           | -        |          |
| onClose             | 选项卡被关闭时的事件回调<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 关闭的选项卡的 key                                                                                             | (key: string) => void                                                                                           | -        |          |
| tabRender           | 自定义选项卡模板渲染函数<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 当前 Tab.Item 的 key 值<br/>_props_: 传给 Tab.Item 的所有属性键值对返回值<br/>**返回值**:<br/>- 返回自定义组件 | (key: string, props: Record\<string, unknown>) => ReactNode                                                     | -        |          |
| popupProps          | 弹层属性透传，只有当 excessMode 为 dropdown 时生效                                                                                                                                  | ComponentPropsWithRef\<typeof Popup>                                                                            | -        |          |
| icons               | 自定义 icon                                                                                                                                                                         | {<br/> dropdown?: string \| ReactNode;<br/> prev?: string \| ReactNode;<br/> next?: string \| ReactNode;<br/> } | -        |          |
| showAdd             | 展示新增按钮                                                                                                                                                                        | boolean                                                                                                         | -        |          |
| onAdd               | 新增的事件回调                                                                                                                                                                      | () => void                                                                                                      | -        |          |
| addIcon             | 自定义添加按钮                                                                                                                                                                      | ReactNode                                                                                                       | -        |          |

### Tab.Item

| 参数         | 说明                             | 类型                                                     | 默认值 | 是否必填 |
| ------------ | -------------------------------- | -------------------------------------------------------- | ------ | -------- |
| title        | 选项卡标题                       | ReactNode                                                | -      |          |
| closeable    | 单个选项卡是否可关闭             | boolean                                                  | false  |          |
| disabled     | 选项卡是否被禁用                 | boolean                                                  | false  |          |
| style        | 导航栏单个选项卡样式             | CSSProperties                                            | -      |          |
| className    | 导航栏单个选项卡样式类           | string                                                   | -      |          |
| onClick      | 导航栏单个选项卡点击时的回调     | (key: string, e: React.MouseEvent\<HTMLElement>) => void | -      |          |
| onMouseEnter | 导航栏单个选项卡鼠标移入时的回调 | (key: string, e: React.MouseEvent\<HTMLElement>) => void | -      |          |
| onMouseLeave | 导航栏单个选项卡鼠标移出时的回调 | (key: string, e: React.MouseEvent\<HTMLElement>) => void | -      |          |
| children     | 子元素                           | React.ReactNode                                          | -      |          |

## 无障碍键盘操作指南

| 按键        | 说明                 |
| :---------- | :------------------- |
| Right Arrow | 切换至前一项Tab.Item |
| Left Arrow  | 切换至后一项Tab.Item |


---


## table

# zh-CN order=23

# 无障碍支持

通过键盘方向键浏览表格。

# en-US order=23

# Accessibility

Browse the table by keyboard arrow keys.


---


## table

# zh-CN order=17

# 扩展

通过Table暴露的子组件进行扩展

# en-US order=17

# Extended

You can extend Table through subcomponents exposed by Table.


---


## table

# zh-CN order=0

# 简单

简单的表格渲染

# en-US order=0

# Simple

Simple table usage.


---


## table

# zh-CN order=0

# 通过columns设置列

通过 `columns` 参数设置列

# en-US order=0

# Simple

Set table columns via `columns`


---


## table

# zh-CN order=2

# 选择可控

演示全选和单选受控的功能

# en-US order=2

# Selection under control

Demo all selection and single selection under control.


---


## table

# zh-CN order=7

# 行列合并

通过 cellProps 进行列合并。

# en-US order=7

# Consolidation

Merging column through cellProps.


---


## table

# zh-CN order=7

# 行列合并与锁列

锁列会可能会影响行列合并的 `colIndex`，`lock='left'`的列会被提升到第0列，多个左锁列按照出现的先后顺序，从0到1标记列索引；
`lock='right'`的列会被提升到最后一列，多个右锁列按照出现顺序，从 `lastIndex - n` 到 `lastIndex` 标记列索引。

# en-US order=7

# Merge cell with lock columns

Merging column through cellProps.


---


## table

# zh-CN order=15

# 定制列

定制显示的表格列数

# en-US order=15

# Customize columns

Customized number of table columns.


---


## table

# zh-CN order=25

# 十字参考轴

适用于表头比较复杂，需要做表头分类的场景。

# en-US order=25

# Crossline

It is usually used in the case of header is complex and needs to be classified.


---


## table

# zh-CN order=8

# 增删改查

演示对表格的增删改查

# en-US order=8

# Add, delete and change

Demo the addition, deletion and change of the table.


---


## table

# zh-CN order=20

# 自定义 Loading 组件

# en-US order=20

# Customize Loading Component


---


## table

# zh-CN order=24

# 拖拽排序

可拖拽的表格。拖拽功能的实现依赖 react-dnd@7.x 及 react-dnd-html5-backend@7.x， 它要求 react react-dom 版本高于 16.3.x。在线 Demo 可以参考 https://codesandbox.io/s/draggable-table-drt4m

# en-US order=24

# Simple

Dragable table with sort. It requires react-dnd@7.x, react-dnd-html5-backend@7.x, react@16.3.x and react-dom@16.3.x. Online demo: https://codesandbox.io/s/draggable-table-drt4m


---


## table

# zh-CN order=23

# 可编辑的表格

单元格可编辑的表格

# en-US order=23

# Editable table

Editable table


---


## table

# zh-CN order=5

# 可展开

可以通过 `expandedRowRender` 额外渲染行

# en-US order=5

# Expandable

You can render expanded row by `expandedRowRender`.


---


## table

# zh-CN order=6

# 可展开-复杂

可以通过 `expandedRowRender` 额外渲染行，但是会包含复杂的组件, 可通过 `expandedIndexSimulate` 设置 index 类型

# en-US Complex%0A%0A-+order=6

# Expandable

You can render expanded row by `expandedRowRender`, but will contain complex components.


---


## table

# zh-CN order=6

# 可展开-锁列

`Table.StickyLock` 模式下(IE不支持，会fallback到旧有逻辑)，展开行的可视区域宽度与 `Table` 占屏幕宽度保持一致, 本模式下 `expandedRowIndent` 为 `[0, 0]`，不可修改。

# en-US order=6

# Expandable

(Can't work with IE)When you use `Table.StickyLock`, the width of expanded row will be the same as the width of table take in screen. `expandedRowIndent` will be `[0, 0]`, and it can't be modified.


---


## table

# zh-CN order=3

# 排序与过滤

示例演示了排序和过滤的特性。你可以通过给 `Table.Column` 设置 `sortDirections={['desc', 'asc', 'default']}` 来实现升序、降序、默认，三种状态的循环;

还可以通过给 `Table` 设置 `sort` 属性，用受控的方式，默认设置初始值

# en-US order=3

# Sorting and filtering

Demo the function of sorting and filtering.


---


## table

# zh-CN order=9

# 固定表头

表格可以固定表头,支持sticky方式

# en-US order=9

# Fixed table header

Table header can be fixed, support sticky.


---


## table

# zh-CN order=21

# 自定义Row/Cell

可以重写部分原生属性，比如className style onDoubleClick等。

# en-US order=21

# custom Row/Cell

You can overwrite parts of native attributes, such as className, style, onDoubleClick and so on.


---


## table

# zh-CN order=10

# 分组列表

分组列表展现

# en-US order=10

# Group list

Demo the Group list.


---


## table

# zh-CN order=14

# 锁列

演示表格锁列的功能。锁列不生效？点击 https://fusion.design/help.html#/faq 查看常见原因及有效解决方案

# en-US order=14

# Lock column

Demo the function of lock columns.


---


## table

# zh-CN order=19

# 混合模式

演示了tree模式和rowSelection模式混合

# en-US order=19

# Mixed mode

Demo mixing of tree mode and rowSelection mode.


---


## table

# zh-CN order=12

# 多表头

多个表头

# en-US order=12

# Multi table header

Demo multiple table headers.


---


## table

# zh-CN order=11

# 分页

与分页结合

# en-US order=11

# Pagination

Using with Pagination.


---


## table

# zh-CN order=18

# 重设列的尺寸

推荐使用 `asyncResizable` 和 `onResizeChange` 调整列宽。如果左右锁列的列宽需要调整，请使用 `Table.StickyLock`.

# en-US order=18

# Resize the column

Resize the column by onResizeChange.


---


## table

# zh-CN %E5%A4%8D%E6%9D%82%0A%0A-+order=18&debug=true

# 重设列的尺寸

推荐使用 `asyncResizable` 和 `onResizeChange` 调整列宽。如果左右锁列的列宽需要调整，请使用 `Table.StickyLock`.

# en-US order=18

# Resize the column

Resize the column by onResizeChange.


---


## table

# zh-CN order=4

# 选择框属性

通过 rowSelection.getProps 来控制选择框属性

# en-US order=4

# Checkbox properties

Controlling checkbox properties with rowSelection.getProps


---


## table

# zh-CN order=1

# 可选择

表格可选择功能

# en-US order=1

# Selectable

Demo the selectable table.


---


## table

# zh-CN order=9&debug=true

# 固定表头

表格可以固定表头,支持 sticky 方式

# en-US order=9

# Fixed table header

Table header can be fixed, support sticky.


---


## table

# zh-CN %E5%A4%8D%E6%9D%82%E6%A8%A1%E5%BC%8F%0A%0A-+order=27&debug=true

# 新锁列

`Table.StickyLock` 一些常用的复杂模式

# en-US Complex%0A%0A-+order=27

# StickyLock

Some complex usage of `Table.StickyLock`


---


## table

# zh-CN order=16

# 样式

自定义表格样式：

-   在`Table`上，你可以通过API来设置斑马线、是否显示边框等；
-   在 `Table.Column` 上，你可以通过 `align` 设置内容居左中右，`wordBreak` 设置内容换行模式（默认是任意位置均可换行，可以为英文句子类设置值`word`）

# en-US order=16

# Style

Customize table borders


---


## table

# zh-CN order=26

# 树表格逐级加载

演示 TreeTable 如何进行逐级加载

# en-US order=26

# Tree Table with load

Tree Table with load.


---


## table

# zh-CN order=13

# 虚拟滚动

使用 `useVirtual` 开启虚拟滚动，`scrollToRow` 滚动到指定行

# en-US order=13

# Virtual scroll

Use `useVirtual` to enable virtual scrolling and `scrollToRow` scrolls to the specified column


---


## table

# zh-CN order=28

# 虚拟滚动与行合并

虚拟滚动会卸载滚动到视区之外的行，行合并利用 td 元素的 rowSpan 属性，需要在合并的第一行设置 rowSpan 属性，若因滚动视区外卸载了该行，则会导致行合并失效，可以使用 `keepForwardRenderRows` 设置向前保留一定行数不被卸载，从而使行合并始终生效（设置 `keepForwardRenderRows` 大于 max rowSpan 即可）

# en-US order=28

# Simple

Virtual scrolling will unload rows scrolled outside the viewport. Row merging uses the rowSpan attribute of the td element. The rowSpan attribute needs to be set on the first row of the merge. If the row is unloaded due to scrolling outside the viewport, the row merging will fail. , you can use `keepForwardRenderRows` to set a certain number of rows to be reserved forward without being unloaded, so that row merging will always take effect (just set `keepForwardRenderRows` to be greater than max rowSpan)


---


## table

# Table

-   category: Components
-   family: DataDisplay
-   chinese: 表格
-   cols: 1
-   type: 展示

---

展示行列数据。

## 何时使用

-   Table 负责将数据呈现为高度可定制和具备可访问性的 HTML 表格，其核心功能为将结构化的数据使用表格的方式展现；
-   可以使用各种参数来向表格中加入一些特性，比如排序，过滤，滚动，锁列等。

### Table.StickyLock

这是 `1.21` 版本推出的子组件，它与 `Table` 用法、API完全一样，只是优化了锁列的实现，推荐升级。

区分如下：

-   旧版本锁列通过两层dom来模拟左、右锁列的列，因此滚动、行高的同步等都需要额外逻辑的，逻辑较重;
-   新版本 `Table.StickyLock` 通过 `position: sticky` 来实现锁列，滚动、行高等行为都通过浏览器实现，逻辑轻量;

建议用户在新的页面中使用 `Table.StickyLock`，如果没有深度的样式定制（例如选择到 `.next-table-lock-left` 这一层级）,也可以把现有的 `Table` 升级到 `Table.StickyLock`

## FAQ

### `rowSelection` 模式，选择任意一个都是全选？

给定的数据源中的属性需要有一个唯一标示该条数据的主键，默认值为id，可通过 `primaryKey` 更改 e.g.`<Table primaryKey='myId'></Table>`。

### `rowSelection` 模式，如何设置默认选中/禁用？

通过受控模式，设置 `rowSelection.selectedRowKeys` 可以默认选中选中；通过 `rowSelection.getProps` 可以自定义每一行checkbox的props，具体可搜索demo`选择可控`。

### `rowSelection` 模式，如何屏蔽全选按钮/自定义全选按钮?

通过`rowSelection.titleProps` 可以自定义选择列的表头的props，可通过 `style: {display: 'none'}` 屏蔽全选按钮；此外还有 `rowSelection.titleAddons` `rowSelection.columnProps`等属性，具体用法可搜索demo `可选择`。

### 支持行的双击事件/设置每一行的样式？处理整行点击？

通过 `rowProps` 属性，重写行支持的原生属性，比如`className style onDoubleClick`等；通过 `onRowClick` 处理整行点击。

### 已知问题

-   分组 Table 不支持在 Hover 状态和选中状态下显示背景色，无法合并单元格；
-   分组 Table ，`<Table fixedHeader/>` 没有效果，header不会固定， `<Table fixedHeader stickyHeader />` 才有效果，header可以sticky到页面上

## 如何使用

基本的 Table 包含行和列，使用 Table.Column 来定义列的信息，使用传入的 dataSource 属性数据来创建行。

下面的代码将会创建一行两列的数据表：

```jsx
import { Table } from '@alifd/next';

const dataSource = [{id: 1, time: '2016'}];
ReactDOM.render(
    <Table.StickyLock dataSource={dataSource}>
        <Table.Column title="Id" dataIndex="id"/>
        <Table.Column title="Time" dataIndex="time"/>
    </Table.StickyLock>, mountNode);
```

### 列配置

Table.Column 提供了非常多的配置属性用于自定义列，最常见的就是使用`cell`自定义单元格的渲染逻辑. 其他的配置选项可以参考下面的 Table.Column 的 API。

下面的代码会让`cell`根据值渲染不同的视图：

```jsx
import { Table } from '@alifd/next';

const dataSource = [{id: 1, time: '2016'}];
const renderTime = value => {
    if (value === '2016') {
        return '今年';
    }
    return value;
};
ReactDOM.render(
    <Table dataSource={dataSource}>
        <Table.Column title="Id" dataIndex="id"/>
        <Table.Column title="Time" dataIndex="time" cell={renderTime}/>
    </Table>, mountNode);
```

### 多表头

使用 Table.ColumnGroup 包裹 Table.Column 来创建有多个表头的表格。

```jsx
import { Table } from '@alifd/next';

const dataSource = [{id: 1, time: '2016'}];
ReactDOM.render(
    <Table dataSource={dataSource}>
        <Table.ColumnGroup>
            <Table.Column title="Id" dataIndex="id"/>
            <Table.Column title="Time" dataIndex="time"/>
        </Table.ColumnGroup>
        <Table.ColumnGroup>
            <Table.Column title="Id" dataIndex="id"/>
        </Table.ColumnGroup>
    </Table>, mountNode);
```

## API

### Table

| 参数                    | 说明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | 类型                          | 默认值      | 版本支持    |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------- | -------- | ------- |
| tableLayout           | 表格元素的 table-layout 属性，设为 fixed 表示内容不会影响列的布局<br/><br/>**可选值**:<br/>'fixed', 'auto'                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Enum                        | -        |         |
| size                  | 尺寸 small为紧凑模式<br/><br/>**可选值**:<br/>'small', 'medium'                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Enum                        | 'medium' |         |
| tableWidth            | 表格的总长度，可以这么用：设置表格总长度 、设置部分列的宽度，这样表格会按照剩余空间大小，自动其他列分配宽度                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Number                      | -        |         |
| dataSource            | 表格展示的数据源                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Array                       | \[]      |         |
| onRowClick            | 点击表格每一行触发的事件<br/><br/>**签名**:<br/>Function(record: Object, index: Number, e: Event) => void<br/>**参数**:<br/>_record_: {Object} 该行所对应的数据<br/>_index_: {Number} 该行所对应的序列<br/>_e_: {Event} DOM事件对象                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Function                    | () => {} |         |
| onRowMouseEnter       | 悬浮在表格每一行的时候触发的事件<br/><br/>**签名**:<br/>Function(record: Object, index: Number, e: Event) => void<br/>**参数**:<br/>_record_: {Object} 该行所对应的数据<br/>_index_: {Number} 该行所对应的序列<br/>_e_: {Event} DOM事件对象                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Function                    | () => {} |         |
| onRowMouseLeave       | 离开表格每一行的时候触发的事件<br/><br/>**签名**:<br/>Function(record: Object, index: Number, e: Event) => void<br/>**参数**:<br/>_record_: {Object} 该行所对应的数据<br/>_index_: {Number} 该行所对应的序列<br/>_e_: {Event} DOM事件对象                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Function                    | () => {} |         |
| onSort                | 点击列排序触发的事件<br/><br/>**签名**:<br/>Function(dataIndex: String, order: String) => void<br/>**参数**:<br/>_dataIndex_: {String} 指定的排序的字段<br/>_order_: {String} 排序对应的顺序, 有`desc`和`asc`两种                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Function                    | () => {} |         |
| onFilter              | 点击过滤确认按钮触发的事件<br/><br/>**签名**:<br/>Function(filterParams: Object) => void<br/>**参数**:<br/>_filterParams_: {Object} 过滤的字段信息                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Function                    | () => {} |         |
| onResizeChange        | 重设列尺寸的时候触发的事件<br/><br/>**签名**:<br/>Function(dataIndex: String, value: Number) => void<br/>**参数**:<br/>_dataIndex_: {String} 指定重设的字段<br/>_value_: {Number} 列宽变动的数值                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Function                    | () => {} |         |
| rowProps              | 设置每一行的属性，如果返回值和其他针对行操作的属性冲突则无效。<br/><br/>**签名**:<br/>Function(record: Object, index: Number) => Object<br/>**参数**:<br/>_record_: {Object} 该行所对应的数据<br/>_index_: {Number} 该行所对应的序列<br/>**返回值**:<br/>{Object} 需要设置的行属性<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Function                    | () => {} |         |
| cellProps             | 设置单元格的属性，通过该属性可以进行合并单元格<br/><br/>**签名**:<br/>Function(rowIndex: Number, colIndex: Number, dataIndex: String, record: Object) => Object<br/>**参数**:<br/>_rowIndex_: {Number} 该行所对应的序列<br/>_colIndex_: {Number} 该列所对应的序列<br/>_dataIndex_: {String} 该列所对应的字段名称<br/>_record_: {Object} 该行对应的记录<br/>**返回值**:<br/>{Object} 返回td元素的所支持的属性对象<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Function                    | () => {} |         |
| keepForwardRenderRows | 虚拟滚动时向前保留渲染的行数                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Number                      | 10       |         |
| hasBorder             | 表格是否具有边框                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Boolean                     | true     |         |
| hasHeader             | 表格是否具有头部                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Boolean                     | true     |         |
| isZebra               | 表格是否是斑马线                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Boolean                     | false    |         |
| loading               | 表格是否在加载中                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Boolean                     | false    |         |
| loadingComponent      | 自定义 Loading 组件<br/>请务必传递 props, 使用方式： loadingComponent={props => &lt;Loading {...props}/>}<br/><br/>**签名**:<br/>Function(props: LoadingProps) => React.ReactNode<br/>**参数**:<br/>_props_: {LoadingProps} 需要透传给组件的参数<br/>**返回值**:<br/>{React.ReactNode} 展示的组件<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Function                    | -        |         |
| filterParams          | 当前过滤的的keys,使用此属性可以控制表格的头部的过滤选项中哪个菜单被选中,格式为 {dataIndex: {selectedKeys:\[]}}<br/>示例:<br/>假设要控制dataIndex为id的列的过滤菜单中key为one的菜单项选中<br/>`<Table filterParams={{id: {selectedKeys: ['one']}}}/>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Object                      | -        |         |
| sort                  | 当前排序的字段,使用此属性可以控制表格的字段的排序,格式为{[dataIndex]&#x3A; 'asc'                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | 'desc' } , 例如  {id: 'desc'} | Object   | -       |
| sortIcons             | 自定义排序按钮，例如上下排布的: `{desc: <Icon style={{top: '6px', left: '4px'}} type={'arrow-down'} size="small" />, asc: <Icon style={{top: '-6px', left: '4px'}} type={'arrow-up'} size="small" />}`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Object                      | -        |         |
| columns               | 等同于写子组件 Table.Column ，子组件优先级更高                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Array                       | -        |         |
| emptyContent          | 设置数据为空的时候的表格内容展现                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | ReactNode                   | -        |         |
| primaryKey            | dataSource当中数据的主键，如果给定的数据源中的属性不包含该主键，会造成选择状态全部选中                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Symbol/String               | 'id'     |         |
| expandedRowRender     | 额外渲染行的渲染函数<br/><br/>**签名**:<br/>Function(record: Object, index: Number) => Element<br/>**参数**:<br/>_record_: {Object} 该行所对应的数据<br/>_index_: {Number} 该行所对应的序列<br/>**返回值**:<br/>{Element} 渲染内容<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Function                    | -        |         |
| rowExpandable         | 设置行是否可展开，设置 false 为不可展开<br/><br/>**签名**:<br/>Function(record: Object, index: Number) => Boolean<br/>**参数**:<br/>_record_: {Object} 该行所对应的数据<br/>_index_: {Number} 该行所对应的序列<br/>**返回值**:<br/>{Boolean} 是否可展开<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Function                    | -        |         |
| expandedRowIndent     | 额外渲染行的缩进, 是个二维数组(eg:[1,1]) 分别表示左右两边的缩进                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Array                       | -        |         |
| hasExpandedRowCtrl    | 是否显示点击展开额外渲染行的+号按钮                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Boolean                     | -        |         |
| getExpandedColProps   | 设置额外渲染行的属性<br/><br/>**签名**:<br/>Function(record: Object, index: Number) => Object<br/>**参数**:<br/>_record_: {Object} 该行所对应的数据<br/>_index_: {Number} 该行所对应的序列<br/>**返回值**:<br/>{Object} 额外渲染行的属性<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Function                    | -        |         |
| openRowKeys           | 当前展开的 Expand行 或者 Tree行 , 传入此属性为受控状态，一般配合 onRowOpen 使用                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Array                       | -        |         |
| defaultOpenRowKeys    | 默认情况下展开的 Expand行 或者 Tree行，非受控模式                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Array                       | -        | 1.23.22 |
| onRowOpen             | 在 Expand行 或者 Tree行 展开或者收起的时候触发的事件<br/><br/>**签名**:<br/>Function(openRowKeys: Array, currentRowKey: String, expanded: Boolean, currentRecord: Object) => void<br/>**参数**:<br/>_openRowKeys_: {Array} 展开的渲染行的key<br/>_currentRowKey_: {String} 当前点击的渲染行的key<br/>_expanded_: {Boolean} 当前点击是展开还是收起<br/>_currentRecord_: {Object} 当前点击额外渲染行的记录                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Function                    | -        |         |
| fixedHeader           | 表头是否固定，该属性配合maxBodyHeight使用，当内容区域的高度超过maxBodyHeight的时候，在内容区域会出现滚动条                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Boolean                     | -        |         |
| maxBodyHeight         | 最大内容区域的高度,在`fixedHeader`为`true`的时候,超过这个高度会出现滚动条                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Number/String               | -        |         |
| rowSelection          | 是否启用选择模式<br/><br/>**属性**:<br/>_getProps_: {Function} `Function(record, index)=>Object` 获取selection的默认属性<br/>_onChange_: {Function} `Function(selectedRowKeys:Array, records:Array)` 选择改变的时候触发的事件，**注意:** 其中records只会包含当前dataSource的数据，很可能会小于selectedRowKeys的长度。<br/>_onSelect_: {Function} `Function(selected:Boolean, record:Object, records:Array)` 用户手动选择/取消选择某行的回调<br/>_onSelectAll_: {Function} `Function(selected:Boolean, records:Array)` 用户手动选择/取消选择所有行的回调<br/>_selectedRowKeys_: {Array} 设置了此属性,将rowSelection变为受控状态,接收值为该行数据的primaryKey的值<br/>_mode_: {String} 选择selection的模式, 可选值为`single`, `multiple`，默认为`multiple`<br/>_columnProps_: {Function} `Function()=>Object` 选择列 的props，例如锁列、对齐等，可使用`Table.Column` 的所有参数<br/>_titleProps_: {Function} `Function()=>Object` 选择列 表头的props，仅在 `multiple` 模式下生效<br/>_titleAddons_: {Function} `Function()=>Node` 选择列 表头添加的元素，在`single` `multiple` 下都生效 | Object                      | -        |         |
| stickyHeader          | 表头是否是sticky                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Boolean                     | -        |         |
| offsetTop             | 距离窗口顶部达到指定偏移量后触发                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Number                      | -        |         |
| affixProps            | affix组件的的属性                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Object                      | -        |         |
| indent                | 在tree模式下的缩进尺寸， 仅在isTree为true时候有效                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Number                      | -        |         |
| isTree                | 开启Table的tree模式, 接收的数据格式中包含children则渲染成tree table                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Boolean                     | -        |         |
| useVirtual            | 是否开启虚拟滚动                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Boolean                     | -        |         |
| scrollToRow           | 滚动到第几行，需要保证行高相同。1.22.15 版本之前仅在虚拟滚动场景下生效，之后在所有情况下生效                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Number                      | -        | 1.22.15 |
| onBodyScroll          | 在内容区域滚动的时候触发的函数<br/><br/>**签名**:<br/>Function() => void                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Function                    | -        |         |
| expandedIndexSimulate | 开启时，getExpandedColProps() / rowProps() / expandedRowRender() 的第二个参数 index (该行所对应的序列) 将按照01,2,3,4...的顺序返回，否则返回真实index(0,2,4,6... / 1,3,5,7...)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Boolean                     | false    |         |
| crossline             | 在 hover 时出现十字参考轴，适用于表头比较复杂，需要做表头分类的场景。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Boolean                     | false    |         |

### Table.Column

| 参数              | 说明                                                                                                                                                                                                              | 类型                              | 默认值                               | 版本支持 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------- | --------------------------------- | ---- |
| dataIndex       | 指定列对应的字段，支持`a.b`形式的快速取值                                                                                                                                                                                         | String                          | -                                 |      |
| cell            | 行渲染的逻辑<br/>value, rowIndex, record, context四个属性只可读不可被更改<br/>Function(value, index, record) => Element                                                                                                           | ReactElement/ReactNode/Function | value => value                    |      |
| title           | 表头显示的内容                                                                                                                                                                                                         | ReactElement/ReactNode/Function | -                                 |      |
| htmlTitle       | 写到 header 单元格上的title属性                                                                                                                                                                                          | String                          | -                                 |      |
| sortable        | 是否支持排序                                                                                                                                                                                                          | Boolean                         | -                                 |      |
| sortDirections  | 排序的方向。<br/>设置 ['desc', 'asc']，表示降序、升序<br/>设置 ['desc', 'asc', 'default']，表示表示降序、升序、不排序                                                                                                                           | Array&lt;Enum>                  | -                                 | 1.23 |
| width           | 列宽，注意在锁列的情况下一定需要配置宽度                                                                                                                                                                                            | Number/String                   | -                                 |      |
| align           | 单元格的对齐方式<br/><br/>**可选值**:<br/>'left', 'center', 'right'                                                                                                                                                        | Enum                            | -                                 |      |
| alignHeader     | 单元格标题的对齐方式, 不配置默认读取align值<br/><br/>**可选值**:<br/>'left', 'center', 'right'                                                                                                                                       | Enum                            | -                                 |      |
| filters         | 生成标题过滤的菜单, 格式为`[{label:'xxx', value:'xxx'}]`                                                                                                                                                                    | Array&lt;Object>                | -                                 |      |
| filterMode      | 过滤的模式是单选还是多选<br/><br/>**可选值**:<br/>'single', 'multiple'                                                                                                                                                         | Enum                            | 'multiple'                        |      |
| filterMenuProps | filter 模式下传递给 Menu 菜单的属性， 默认继承 `Menu` 组件的API<br/><br/>**属性**:<br/>_subMenuSelectable_: {Boolean} 默认为`false` subMenu是否可选择<br/>_isSelectIconRight_: {Boolean} 默认为`false` 是否将选中图标居右。注意：SubMenu 上的选中图标一直居左，不受此API控制 | Object                          | {     subMenuSelectable: false, } |      |
| lock            | 是否支持锁列,可选值为`left`,`right`, `true`                                                                                                                                                                               | Boolean/String                  | -                                 |      |
| resizable       | 是否支持列宽调整, 当该值设为true，table的布局方式会修改为fixed.                                                                                                                                                                        | Boolean                         | false                             |      |
| asyncResizable  | （推荐使用）是否支持异步列宽调整, 当该值设为true，table的布局方式会修改为fixed.                                                                                                                                                                | Boolean                         | false                             | 1.24 |
| colSpan         | header cell 横跨的格数，设置为0表示不出现此 th                                                                                                                                                                                 | Number                          | -                                 |      |
| wordBreak       | 设置该列单元格的word-break样式，对于id类、中文类适合用all，对于英文句子适合用word<br/><br/>**可选值**:<br/>'all'(all)<br/>'word'(word)                                                                                                            | Enum                            | all                               | 1.23 |

### Table.ColumnGroup

| 参数    | 说明      | 类型                              | 默认值            |
| ----- | ------- | ------------------------------- | -------------- |
| title | 表头显示的内容 | ReactElement/ReactNode/Function | 'column-group' |

### Table.GroupHeader

| 参数                              | 说明                                    | 类型                              | 默认值      |
| ------------------------------- | ------------------------------------- | ------------------------------- | -------- |
| cell                            | 行渲染的逻辑                                | ReactElement/ReactNode/Function | () => '' |
| hasChildrenSelection            | 是否在Children上面渲染selection              | Boolean                         | false    |
| hasSelection                    | 是否在GroupHeader上面渲染selection           | Boolean                         | true     |
| useFirstLevelDataWhenNoChildren | 当 dataSouce 里没有 children 时，是否使用内容作为数据 | Boolean                         | false    |

### Table.GroupFooter

| 参数   | 说明     | 类型                              | 默认值      |
| ---- | ------ | ------------------------------- | -------- |
| cell | 行渲染的逻辑 | ReactElement/ReactNode/Function | () => '' |


---


## tag

# zh-CN order=6

# 无障碍支持

组件已支持无障碍。关于键盘操作请参考 [#无障碍键盘操作指南](#无障碍键盘操作指南)

# en-US order=6

# Accessibility

Components already support accessibility.Please refer to `ARIA and KeyBoard` for keyboard operation.


---


## tag

# zh-CN order=0

# 基本

基本的标签

# en-US order=0

# Basic Usage

basic tag


---


## tag

# zh-CN order=5

# 可关闭

通过点击标签或者 closeIcon 来隐藏标签

# en-US order=5

# Closeable Tag

close tag by clicking tag element or close icon


---


## tag

# zh-CN order=3

# 彩色标签

带颜色的标签，如果颜色不能满足，可以自定义颜色 (只能是实心标签)

# en-US order=3

# Colorful Tag

colorful tag & tag with custom color


---


## tag

# zh-CN order=2

# 带有图标

根据自身需要设置 icon

# en-US order=2

# Basic Usage

add `Icon` in tag if it's necessary


---


## tag

# zh-CN order=4

# 可选中

待选中状态的标签，通过点击来切换

# en-US order=4

# Selectable Tag

click tag to toggle select status


---


## tag

# zh-CN order=1

# 尺寸

三种尺寸的 `Tag`

# en-US order=1

# Size

three sizes of `Tag`


---


## tag

# Tag

-   category: Components
-   family: DataDisplay
-   chinese: 标签
-   type: 展示

---

标签用于标记事物的属性和维度，或者可以使用标签来对一组事物分类。

## 何时使用

-   用于标记事物的属性和维度。
-   进行分类。

## 如何使用

1.  虽然可以设置 `size` 属性取值 `large`，但该值只是为了兼容表单场景，实际取值时 `large` 等同于 `medium`。
2.  不建议在 Tag 中使用大段文本。

## API

### Tag

| 参数        | 说明                                                                          | 类型                                                                                                   | 默认值   | 是否必填 | 支持版本 |
| ----------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | -------- | -------- | -------- |
| type        | 标签的类型                                                                    | 'normal' \| 'primary'                                                                                  | 'normal' |          | -        |
| size        | 标签的尺寸                                                                    | 'small' \| 'medium' \| 'large'                                                                         | -        |          | -        |
| color       | 标签颜色，目前支持：blue、green、orange、red、turquoise、yellow 和 hex 颜色值 | string                                                                                                 | -        |          | 1.19.0   |
| animation   | 是否开启动效                                                                  | boolean                                                                                                | false    |          | -        |
| afterAppear | 标签出现动画结束后执行的回调                                                  | (node: HTMLElement) => void                                                                            | -        |          | -        |
| onClick     | 点击回调                                                                      | (<br/> event: React.MouseEvent\<HTMLDivElement> \| React.KeyboardEvent\<HTMLDivElement><br/> ) => void | -        |          | -        |

### Tag.Closeable

继承 Tag 的所有属性

| 参数       | 说明                                                                                                                       | 类型                                                     | 默认值 | 是否必填 |
| ---------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- | ------ | -------- |
| closeArea  | closeable 标签的 onClose 响应区域                                                                                          | CloseArea                                                | 'tail' |          |
| onClose    | 点击关闭按钮时的回调<br/><br/>**签名**:<br/>**参数**:<br/>_from_: 事件来源<br/>**返回值**:<br/>true 则关闭，false 阻止关闭 | (from: CloseArea, node?: HTMLElement \| null) => boolean | -      |          |
| afterClose | 标签关闭后执行的回调                                                                                                       | (node: HTMLElement \| null) => void                      | -      |          |

### Tag.Selectable

继承 Tag 的所有属性

| 参数           | 说明                             | 类型                                                                                                                      | 默认值 | 是否必填 |
| -------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------ | -------- |
| checked        | 标签是否被选中，受控用法         | boolean                                                                                                                   | -      |          |
| defaultChecked | 标签是否默认被选中，非受控用法。 | boolean                                                                                                                   | -      |          |
| onChange       | 选中状态变化时触发的事件         | (<br/> checked: boolean,<br/> e: React.MouseEvent\<HTMLDivElement> \| React.KeyboardEvent\<HTMLDivElement><br/> ) => void | -      |          |

### CloseArea

示例：

-   tag: 标签体
-   tail: 关闭按钮

```typescript
export type CloseArea = 'tag' | 'tail';
```

## 无障碍键盘操作指南

| 按键  | 说明                     |
| :---- | :----------------------- |
| SPACE | 选择，取消或删除当前标签 |


---


## time-picker

# zh-CN order=0

# 基本

最简单的用法。

# en-US order=0

# Basic

Basic usage.


---


## time-picker

# zh-CN order=1

# 默认值

可以通过 `defaultValue` 传入默认时间值，并且可以通过选择改变该值。`onChange` 回调参数的值的类型取决于 `defaultValue` 的类型。

# en-US order=1

# Default value

Setting default value by passing `defaultValue`.


---


## time-picker

# zh-CN order=3

# 禁用时分秒

禁用全部和禁用部分选择项

# en-US order=3

# Disable cells

Disable some time celles.


---


## time-picker

# zh-CN order=6

# 结合 Field 使用

配合 Field 使用

# en-US order=6

# With Field

Use TimePicker with Field.


---


## time-picker

# zh-CN order=4

# 时间格式

可以通过 `format` 属性格式化时间值，此外该属性还会影响到时间列的展示。

# en-US order=4

# Time format

You can control the time format by `format`, it will also effect the display of time panel.


---


## time-picker

# zh-CN order=5

# 自定义渲染时间选择菜单

可以通过 `renderTimeMenuItems` 来自定义渲染下拉菜单每一项。

# en-US order=5

# Custom Render Time Menu

Render time menu by `renderTimeMenuItems`.


---


## time-picker

# zh-CN order=1

# 尺寸

TimePicker 使用和 Input 组件相同的输入框尺寸，可以通过 `size` 属性进行设置。

# en-US order=1

# Size

Setting picker size by `size`.


---


## time-picker

# zh-CN order=5

# 步长

可以通过 `hourStep`, `minuteStep`, `secondStep` 分别设置时分秒的选项间隔。

# en-US order=5

# Time step

Setting time interval by `hourStep`, `minuteStep`, `secondStep`.


---


## time-picker

# zh-CN order=2

# 受控

通过 `value` 和 `onChange` 实现受控，仅支持通过选择实现受控。

# en-US order=2

# Controlled

Creating controlled TimePikcer by `value` and `onChange`.


---


## time-picker

# TimePicker

-   category: Components
-   family: DataEntry
-   chinese: 时间选择框
-   type: 表单

---

时间选择器。

## 何时使用

当用户需要输入一个时间，可以点击输入框，在弹出的时间选择面板上操作。时间选择面板仅支持 24 小时制。`format` 支持的时间格式如下：

| 格式   | 例子    | 说明          |
| ------ | ------- | ------------- |
| `H HH` | `0..23` | 时，24 小时制 |
| `m mm` | `0..59` | 分            |
| `s ss` | `0..59` | 秒            |

组件默认使用 moment 实例作为输入输出值，推荐使用结合 moment 的方式使用组件。此外，组件也支持传入时间字符串的方式，例如直接传入 "12:00:00"。用户传入什么类型的 value/defaultValue 值，就会在 onChange 中返回相应的类型。

## API

### TimePicker

| 参数                | 说明                                                                                                                                                                                                   | 类型                                                                                                                                           | 默认值 | 是否必填 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------ | -------- |
| label               | 按钮的文案                                                                                                                                                                                             | React.ReactNode                                                                                                                                | -      |          |
| state               | 输入框状态                                                                                                                                                                                             | 'error' \| 'success'                                                                                                                           | -      |          |
| placeholder         | 输入框提示                                                                                                                                                                                             | string                                                                                                                                         | -      |          |
| value               | 时间值（moment 对象或时间字符串，受控状态使用）                                                                                                                                                        | string \| Moment \| null                                                                                                                       | -      |          |
| defaultValue        | 时间初值（moment 对象或时间字符串，非受控状态使用）                                                                                                                                                    | string \| Moment                                                                                                                               | -      |          |
| size                | 时间选择框的尺寸                                                                                                                                                                                       | 'small' \| 'medium' \| 'large'                                                                                                                 | -      |          |
| hasClear            | 是否允许清空时间                                                                                                                                                                                       | boolean                                                                                                                                        | -      |          |
| format              | 时间的格式                                                                                                                                                                                             | string                                                                                                                                         | -      |          |
| hourStep            | 小时选项步长                                                                                                                                                                                           | number                                                                                                                                         | -      |          |
| minuteStep          | 分钟选项步长                                                                                                                                                                                           | number                                                                                                                                         | -      |          |
| secondStep          | 秒钟选项步长                                                                                                                                                                                           | number                                                                                                                                         | -      |          |
| disabledHours       | 禁用小时的函数                                                                                                                                                                                         | (index: number) => boolean                                                                                                                     | -      |          |
| disabledMinutes     | 禁用分钟函数                                                                                                                                                                                           | (index: number) => boolean                                                                                                                     | -      |          |
| disabledSeconds     | 禁用秒钟函数                                                                                                                                                                                           | (index: number) => boolean                                                                                                                     | -      |          |
| visible             | 弹层是否显示（受控）                                                                                                                                                                                   | boolean                                                                                                                                        | -      |          |
| defaultVisible      | 弹层默认是否显示（非受控）                                                                                                                                                                             | boolean                                                                                                                                        | -      |          |
| popupContainer      | 弹层容器                                                                                                                                                                                               | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement)                                                                                | -      |          |
| popupAlign          | 弹层对齐方式，详情见 Overlay 文档                                                                                                                                                                      | string                                                                                                                                         | -      |          |
| popupTriggerType    | 弹层触发方式                                                                                                                                                                                           | 'click' \| 'hover'                                                                                                                             | -      |          |
| onVisibleChange     | 弹层展示状态变化时的回调                                                                                                                                                                               | (visible: boolean, reason: string) => void                                                                                                     | -      |          |
| popupStyle          | 弹层自定义样式                                                                                                                                                                                         | React.CSSProperties                                                                                                                            | -      |          |
| popupClassName      | 弹层自定义样式类                                                                                                                                                                                       | string                                                                                                                                         | -      |          |
| popupProps          | 弹层属性                                                                                                                                                                                               | PopupProps                                                                                                                                     | -      |          |
| disabled            | 是否禁用                                                                                                                                                                                               | boolean                                                                                                                                        | -      |          |
| isPreview           | 是否为预览态                                                                                                                                                                                           | boolean                                                                                                                                        | -      |          |
| renderPreview       | 预览态模式下渲染的内容                                                                                                                                                                                 | (value: Moment \| null, props: TimePickerProps) => React.ReactNode                                                                             | -      |          |
| onChange            | 时间值改变时的回调                                                                                                                                                                                     | (value: Moment \| string \| null) => void                                                                                                      | -      |          |
| renderTimeMenuItems | 渲染的可选择时间列表<br/><br/>**签名**:<br/>**参数**:<br/>_list_: 默认渲染的列表<br/>_mode_: 渲染的菜单 hour, minute, second<br/>_value_: 当前时间，可能为 null<br/>**返回值**:<br/>返回需要渲染的数据 | (<br/> list: Array\<TimeMenuListItem>,<br/> mode: TimeMenuProps['mode'],<br/> value: TimeMenuProps['value']<br/> ) => Array\<TimeMenuListItem> | -      |          |
| inputProps          | 自定义输入框属性                                                                                                                                                                                       | InputProps                                                                                                                                     | -      |          |
| popupContent        | 弹层内容                                                                                                                                                                                               | React.ReactNode                                                                                                                                | -      |          |
| followTrigger       | 跟随触发元素                                                                                                                                                                                           | boolean                                                                                                                                        | -      |          |

## 无障碍键盘操作指南

| 按键            | 说明                                                                            |
| :-------------- | :------------------------------------------------------------------------------ |
| Enter           | 打开时间选择框                                                                  |
| Esc             | 关闭时间选择框                                                                  |
| Up              | 输入上一秒的时间 （如果 `disabledMinutes={true}` 则可能是上一分钟或者上一小时） |
| Down            | 输入下一秒的时间 （如果 `disabledMinutes={true}` 则可能是下一分钟或者下一小时） |
| Page Up         | 输入上一分钟的时间                                                              |
| Page Down       | 输入下一分钟的时间                                                              |
| Alt + Page Up   | 输入上一小时的时间                                                              |
| Alt + Page Down | 输入下一小时的时间                                                              |


---


## time-picker2

# zh-CN order=0

# 基本

最简单的用法。

# en-US order=0

# Basic

Basic usage.


---


## time-picker2

# zh-CN order=1

# 默认值

可以通过 `defaultValue` 传入默认时间值，并且可以通过选择改变该值。

> 在 1.x 中，`onChange` 回调参数的值的类型取决于 `defaultValue` 的类型
> 而在 2.x 里，我们废弃了这种难以捉摸的黑魔法，`onChange` 种第一个参数是dayjs类型，第二个参数是被format后的String类型

# en-US order=1

# Default value

Setting default value by passing `defaultValue`.


---


## time-picker2

# zh-CN order=4

# 禁用时分秒

禁用全部和禁用部分选择项

# en-US order=4

# Disable cells

Disable some time celles.


---


## time-picker2

# zh-CN order=10

# 结合 Field 使用

配合 Field 使用

# en-US order=10

# With Field

Use TimePicker2 with Field.


---


## time-picker2

# zh-CN order=5

# 时间格式

可以通过 `format` 属性格式化时间值，此外该属性还会影响到时间列的展示。

# en-US order=5

# Time format

You can control the time format by `format`, it will also effect the display of time panel.


---


## time-picker2

# zh-CN order=6

# 无边框

无边框。

# en-US order=6

# No Border

without border


---


## time-picker2

# zh-CN order=8

# 预设

预设

# en-US order=8

# Preset

preset


---


## time-picker2

# zh-CN order=1

# 范围选择

时间范围选择

# en-US order=1

# Basic

RangePicker of TimePicker.


---


## time-picker2

# zh-CN order=7

# 自定义渲染时间选择菜单

可以通过 `renderTimeMenuItems` 来自定义渲染下拉菜单每一项。

# en-US order=7

# Custom Render Time Menu

Render time menu by `renderTimeMenuItems`.


---


## time-picker2

# zh-CN order=3

# 尺寸

TimePicker2 使用和 Input 组件相同的输入框尺寸，可以通过 `size` 属性进行设置。

# en-US order=3

# Size

Setting picker size by `size`.


---


## time-picker2

# zh-CN order=9

# 步长

可以通过 `hourStep`, `minuteStep`, `secondStep` 分别设置时分秒的选项间隔。

# en-US order=9

# Time step

Setting time interval by `hourStep`, `minuteStep`, `secondStep`.


---


## time-picker2

# zh-CN order=2

# 受控

通过 `value` 和 `onChange` 实现受控，仅支持通过选择实现受控。

# en-US order=2

# Controlled

Creating controlled TimePikcer by `value` and `onChange`.


---


## time-picker2

# TimePicker2

-   category: Components
-   family: DataEntry
-   chinese: 时间选择框2
-   type: 表单

---

## Guide

### 从 `TimePicker` 升级到 `TimePicker2`

1.22版本增加当前组件

功能变化：

-   交互重构，面板和输入框分离，支持预设日期，支持底部扩展等
-   摆脱了对 `moment` 的依赖，使用 `dayjs`
-   新增 `preset` 预设日期
-   新增 `hasBorder` 支持去掉边框

API变化：

-   `onChange` 和 `onOk` 等事件返回日期对象为 `Dayjs` 类型

### 何时使用

当用户需要输入一个时间，可以点击输入框，在弹出的时间选择面板上操作。时间选择面板仅支持 24 小时制。`format` 支持的时间格式如下：

| 格式   | 例子    | 说明          |
| ------ | ------- | ------------- |
| `H HH` | `0..23` | 时，24 小时制 |
| `m mm` | `0..59` | 分            |
| `s ss` | `0..59` | 秒            |

组件默认使用 dayjs 实例作为输入输出值，推荐使用结合 dayjs 的方式使用组件。此外，组件也支持传入时间字符串的方式，例如直接传入 "12:00:00"。用户传入什么类型的 value/defaultValue 值，就会在 onChange 中返回相应的类型。

## API

### TimePicker

| 参数                | 说明                                                                                                                                                                                                                                 | 类型                                                                                                                                           | 默认值     | 是否必填 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------- |
| label               | 按钮的文案                                                                                                                                                                                                                           | ReactNode                                                                                                                                      | -          |          |
| size                | 时间选择框的尺寸                                                                                                                                                                                                                     | 'small' \| 'medium' \| 'large'                                                                                                                 | 'medium'   |          |
| state               | 输入框状态                                                                                                                                                                                                                           | 'error' \| 'success'                                                                                                                           | -          |          |
| hasClear            | 是否允许清空时间                                                                                                                                                                                                                     | boolean                                                                                                                                        | true       |          |
| format              | 时间的格式                                                                                                                                                                                                                           | string                                                                                                                                         | 'HH:mm:ss' |          |
| hourStep            | 小时选项步长                                                                                                                                                                                                                         | number                                                                                                                                         | -          |          |
| minuteStep          | 分钟选项步长                                                                                                                                                                                                                         | number                                                                                                                                         | -          |          |
| secondStep          | 秒钟选项步长                                                                                                                                                                                                                         | number                                                                                                                                         | -          |          |
| renderTimeMenuItems | 渲染的可选择时间列表 [\{ label: '01', value: 1 \}]<br/><br/>**签名**:<br/>**参数**:<br/>_list_: 默认渲染的列表<br/>_mode_: 渲染的菜单 hour, minute, second<br/>_value_: 当前时间，可能为 null<br/>**返回值**:<br/>返回需要渲染的数据 | (<br/> list: Array\<TimeMenuListItem>,<br/> mode: TimeMenuProps['mode'],<br/> value: TimeMenuProps['value']<br/> ) => Array\<TimeMenuListItem> | -          |          |
| visible             | 弹层是否显示（受控）                                                                                                                                                                                                                 | boolean                                                                                                                                        | -          |          |
| defaultVisible      | 弹层默认是否显示（非受控）                                                                                                                                                                                                           | boolean                                                                                                                                        | -          |          |
| popupContainer      | 弹层容器                                                                                                                                                                                                                             | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement)                                                                                | -          |          |
| popupAlign          | 弹层对齐方式，详情见 Overlay 文档                                                                                                                                                                                                    | string                                                                                                                                         | 'tl bl'    |          |
| popupTriggerType    | 弹层触发方式                                                                                                                                                                                                                         | 'click' \| 'hover'                                                                                                                             | 'click'    |          |
| onVisibleChange     | 弹层展示状态变化时的回调                                                                                                                                                                                                             | (visible: boolean, reason?: string) => void                                                                                                    | -          |          |
| popupStyle          | 弹层自定义样式                                                                                                                                                                                                                       | CSSProperties                                                                                                                                  | -          |          |
| popupClassName      | 弹层自定义样式类                                                                                                                                                                                                                     | string                                                                                                                                         | -          |          |
| popupProps          | 弹层属性                                                                                                                                                                                                                             | PopupProps                                                                                                                                     | -          |          |
| followTrigger       | 跟随触发元素                                                                                                                                                                                                                         | boolean                                                                                                                                        | -          |          |
| hasBorder           | 是否有边框                                                                                                                                                                                                                           | boolean                                                                                                                                        | true       |          |
| isPreview           | 是否为预览态                                                                                                                                                                                                                         | boolean                                                                                                                                        | -          |          |
| renderPreview       | 预览态模式下渲染的内容                                                                                                                                                                                                               | (value: ValueType, props: TimePickerProps) => ReactNode                                                                                        | -          |          |
| inputProps          | 自定义输入框属性                                                                                                                                                                                                                     | InputProps                                                                                                                                     | -          |          |
| placeholder         | 输入框提示                                                                                                                                                                                                                           | string                                                                                                                                         | -          |          |
| value               | 时间值（Dayjs 对象或时间字符串，受控状态使用）                                                                                                                                                                                       | string \| Dayjs \| null \| (Dayjs \| null \| string)[]                                                                                         | -          |          |
| defaultValue        | 时间初值（Dayjs 对象或时间字符串，非受控状态使用）                                                                                                                                                                                   | string \| Dayjs \| (Dayjs \| null)[]                                                                                                           | -          |          |
| disabledHours       | 禁用小时的函数，TimePicker.RangePicker 时，函数需要返回 number[]，且函数中没有 index 入参，非 TimePicker.RangePicker 时，函数需要返回 boolean，函数中有 index 入参                                                                   | (index?: number) => boolean \| number[]                                                                                                        | -          |          |
| disabledMinutes     | 禁用分钟函数，TimePicker.RangePicker 时，函数需要返回 number[]，且函数中没有 index 入参，非 TimePicker.RangePicker 时，函数需要返回 boolean，函数中有 index 入参                                                                     | (index?: number) => boolean \| number[]                                                                                                        | -          |          |
| disabledSeconds     | 禁用秒钟函数，TimePicker.RangePicker 时，函数需要返回 number[]，且函数中没有 index 入参，非 TimePicker.RangePicker 时，函数需要返回 boolean，函数中有 index 入参                                                                     | (index?: number) => boolean \| number[]                                                                                                        | -          |          |
| onChange            | 时间值改变时的回调                                                                                                                                                                                                                   | (value: ValueType) => void                                                                                                                     | -          |          |
| preset              | 预设值，会显示在时间面板下面                                                                                                                                                                                                         | PresetType \| PresetType[]                                                                                                                     | -          |          |
| disabled            | 禁用                                                                                                                                                                                                                                 | boolean \| boolean[]                                                                                                                           | false      |          |

### TimePicker.RangePicker

| 参数                | 说明                                                                                                                                                                                                                                 | 类型                                                                                                                                           | 默认值     | 是否必填 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------- |
| label               | 按钮的文案                                                                                                                                                                                                                           | ReactNode                                                                                                                                      | -          |          |
| size                | 时间选择框的尺寸                                                                                                                                                                                                                     | 'small' \| 'medium' \| 'large'                                                                                                                 | 'medium'   |          |
| state               | 输入框状态                                                                                                                                                                                                                           | 'error' \| 'success'                                                                                                                           | -          |          |
| hasClear            | 是否允许清空时间                                                                                                                                                                                                                     | boolean                                                                                                                                        | true       |          |
| format              | 时间的格式                                                                                                                                                                                                                           | string                                                                                                                                         | 'HH:mm:ss' |          |
| hourStep            | 小时选项步长                                                                                                                                                                                                                         | number                                                                                                                                         | -          |          |
| minuteStep          | 分钟选项步长                                                                                                                                                                                                                         | number                                                                                                                                         | -          |          |
| secondStep          | 秒钟选项步长                                                                                                                                                                                                                         | number                                                                                                                                         | -          |          |
| renderTimeMenuItems | 渲染的可选择时间列表 [\{ label: '01', value: 1 \}]<br/><br/>**签名**:<br/>**参数**:<br/>_list_: 默认渲染的列表<br/>_mode_: 渲染的菜单 hour, minute, second<br/>_value_: 当前时间，可能为 null<br/>**返回值**:<br/>返回需要渲染的数据 | (<br/> list: Array\<TimeMenuListItem>,<br/> mode: TimeMenuProps['mode'],<br/> value: TimeMenuProps['value']<br/> ) => Array\<TimeMenuListItem> | -          |          |
| visible             | 弹层是否显示（受控）                                                                                                                                                                                                                 | boolean                                                                                                                                        | -          |          |
| defaultVisible      | 弹层默认是否显示（非受控）                                                                                                                                                                                                           | boolean                                                                                                                                        | -          |          |
| popupContainer      | 弹层容器                                                                                                                                                                                                                             | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement)                                                                                | -          |          |
| popupAlign          | 弹层对齐方式，详情见 Overlay 文档                                                                                                                                                                                                    | string                                                                                                                                         | 'tl bl'    |          |
| popupTriggerType    | 弹层触发方式                                                                                                                                                                                                                         | 'click' \| 'hover'                                                                                                                             | 'click'    |          |
| onVisibleChange     | 弹层展示状态变化时的回调                                                                                                                                                                                                             | (visible: boolean, reason?: string) => void                                                                                                    | -          |          |
| popupStyle          | 弹层自定义样式                                                                                                                                                                                                                       | CSSProperties                                                                                                                                  | -          |          |
| popupClassName      | 弹层自定义样式类                                                                                                                                                                                                                     | string                                                                                                                                         | -          |          |
| popupProps          | 弹层属性                                                                                                                                                                                                                             | PopupProps                                                                                                                                     | -          |          |
| followTrigger       | 跟随触发元素                                                                                                                                                                                                                         | boolean                                                                                                                                        | -          |          |
| hasBorder           | 是否有边框                                                                                                                                                                                                                           | boolean                                                                                                                                        | true       |          |
| isPreview           | 是否为预览态                                                                                                                                                                                                                         | boolean                                                                                                                                        | -          |          |
| renderPreview       | 预览态模式下渲染的内容                                                                                                                                                                                                               | (value: ValueType, props: TimePickerProps) => ReactNode                                                                                        | -          |          |
| inputProps          | 自定义输入框属性                                                                                                                                                                                                                     | InputProps                                                                                                                                     | -          |          |
| disabledHours       | 禁用小时的函数，TimePicker.RangePicker 时，函数需要返回 number[]，且函数中没有 index 入参，非 TimePicker.RangePicker 时，函数需要返回 boolean，函数中有 index 入参                                                                   | (index?: number) => boolean \| number[]                                                                                                        | -          |          |
| disabledMinutes     | 禁用分钟函数，TimePicker.RangePicker 时，函数需要返回 number[]，且函数中没有 index 入参，非 TimePicker.RangePicker 时，函数需要返回 boolean，函数中有 index 入参                                                                     | (index?: number) => boolean \| number[]                                                                                                        | -          |          |
| disabledSeconds     | 禁用秒钟函数，TimePicker.RangePicker 时，函数需要返回 number[]，且函数中没有 index 入参，非 TimePicker.RangePicker 时，函数需要返回 boolean，函数中有 index 入参                                                                     | (index?: number) => boolean \| number[]                                                                                                        | -          |          |
| disabled            | 禁用                                                                                                                                                                                                                                 | boolean \| boolean[]                                                                                                                           | false      |          |
| placeholder         | 输入框提示                                                                                                                                                                                                                           | string \| string[]                                                                                                                             | -          |          |
| value               | 时间值（Dayjs 对象或时间字符串，受控状态使用）                                                                                                                                                                                       | Array\<ConfigType>                                                                                                                             | -          |          |
| defaultValue        | 时间初值（Dayjs 对象或时间字符串，非受控状态使用）                                                                                                                                                                                   | Array\<ConfigType>                                                                                                                             | -          |          |
| onChange            | 时间值改变时的回调                                                                                                                                                                                                                   | (value: Array\<Dayjs>) => void                                                                                                                 | -          |          |
| onOk                | 确定按钮点击时的回调                                                                                                                                                                                                                 | (value: Array\<Dayjs>) => void                                                                                                                 | -          |          |
| preset              | 预设值，会显示在时间面板下面                                                                                                                                                                                                         | PresetType[]                                                                                                                                   | -          |          |

## ARIA and KeyBoard

| 按键            | 说明                                                                            |
| :-------------- | :------------------------------------------------------------------------------ |
| Enter           | 打开时间选择框                                                                  |
| Esc             | 关闭时间选择框                                                                  |
| Up              | 输入上一秒的时间 （如果 `disabledMinutes={true}` 则可能是上一分钟或者上一小时） |
| Down            | 输入下一秒的时间 （如果 `disabledMinutes={true}` 则可能是下一分钟或者下一小时） |
| Page Up         | 输入上一分钟的时间                                                              |
| Page Down       | 输入下一分钟的时间                                                              |
| Alt + Page Up   | 输入上一小时的时间                                                              |
| Alt + Page Down | 输入下一小时的时间                                                              |


---


## timeline

# zh-CN order=0

# 基本用法

最简单的用法。

# en-US order=0

# Basic usage

The simplest usage.


---


## timeline

# zh-CN order=2

# 内容

带内容的用法，分别添加title，content，icon的效果。

# en-US order=2

# Content

With the use of content, add the effects of title, content, and icon, respectively.


---


## timeline

# zh-CN order=4

# 自定义轴节点

自定义时间轴节点。

# en-US order=4

# Custom timeline node

Custom timeline node.


---


## timeline

# zh-CN order=5

# 折叠用法

自定义折叠区域。

# en-US order=5

# Fold

Custom fold area.


---


## timeline

# zh-CN order=6

# 时间轴显示方式

交替显示节点.

# en-US order=6

# display of time axis

alternate timeline node.


---


## timeline

# zh-CN order=1

# 节点状态

设置每个节点不同的状态。

# en-US order=1

# State

Set different states for each node.


---


## timeline

# zh-CN order=3

# 左侧展示时间

设置时间轴左边的内容。

# en-US order=3

# Time in the left side of tiemline

Set the left side of the timeline.


---


## timeline

# Timeline

-   category: Components
-   family: DataDisplay
-   chinese: 时间轴
-   type: 展示

---

垂直展示的时间流信息。

## 何时使用

-   当有一系列信息需要从上至下按时间排列时。
-   需要有一条时间轴进行视觉上的串联时。

## API

### Timeline

| 参数      | 说明                                        | 类型                  | 默认值 | 是否必填 | 支持版本 |
| --------- | ------------------------------------------- | --------------------- | ------ | -------- | -------- |
| fold      | 自定义折叠选项                              | Array\<FoldItem>      | -      |          | -        |
| className | 自定义类名                                  | string                | -      |          | -        |
| animation | 展示动画                                    | boolean               | true   |          | -        |
| mode      | 展示的模式，left 为左，alternate 为交替显示 | 'left' \| 'alternate' | 'left' |          | 1.23.18  |

### Timeline.Item

| 参数      | 说明                                        | 类型                                        | 默认值 | 是否必填 | 支持版本 |
| --------- | ------------------------------------------- | ------------------------------------------- | ------ | -------- | -------- |
| state     | 节点状态                                    | 'done' \| 'process' \| 'error' \| 'success' | 'done' |          | -        |
| icon      | 图标                                        | string                                      | -      |          | -        |
| dot       | 自定义时间轴节点                            | React.ReactNode                             | -      |          | -        |
| time      | 格式化后的时间                              | React.ReactNode                             | -      |          | -        |
| title     | 标题                                        | React.ReactNode                             | -      |          | -        |
| timeLeft  | 左侧时间                                    | React.ReactNode                             | -      |          | -        |
| content   | 右侧内容                                    | React.ReactNode                             | -      |          | -        |
| animation | 展示动画                                    | boolean                                     | true   |          | -        |
| mode      | 展示的模式，left 为左，alternate 为交替显示 | 'left' \| 'alternate'                       | 'left' |          | 1.23.18  |


---


## transfer

# zh-CN order=8

# 无障碍支持

通过设置`locale`去修改对无障碍支持，默认已经设置，请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。
为保证可访问性，需要设置全局唯一的id

# en-US order=6

# Accessibility

By setting the `locale` to modify on accessibility support,The default is set,Please refer to `ARIA and KeyBoard`.
Set a unique `id` for accessibility support.


---


## transfer

# zh-CN order=0

# 基本用法

最简单的用法。

# en-US order=0

# Basic usage

The simplest usage.


---


## transfer

# zh-CN order=1

# 受控

— debug: true

展示受控的用法。

# en-US order=1

# Control

Demo the control usage.


---


## transfer

# zh-CN order=5

# 自定义穿梭按钮

展示自定义穿梭按钮的用法。

# en-US order=5

# Customize

Demo the customize style usage.


---


## transfer

# zh-CN order=7

# 树穿梭框

自定义树形 transfer 面板。

# en-US order=7

# Customize panel

Demo the customize panel usage.


---


## transfer

# zh-CN order=3

# 带搜索框

带搜索框的穿梭框，可以自定义搜索函数。

# en-US order=3

# Search

Demo the search usage.


---


## transfer

# zh-CN order=2

# 简单模式

通过设置 mode 为 'simple'，可以开启简单模式，点击选项即移动。

# en-US order=2

# Simple mode

You can enable the simple mode and click the item to move by setting mode to 'simple'.


---


## transfer

# zh-CN order=4

# 拖拽排序

设置 sortable 属性为 true 后，可拖拽排序左右面板。

# en-US order=4

# Drag and drop sort

After setting the sortable property to true, you can drag and drop the items.


---


## transfer

# zh-CN order=6

# 表格穿梭框

使用 Table 组件作为自定义渲染列表。

# en-US order=7

# Table Transfer

Customize render list with Table component.


---


## transfer

# zh-CN order=7

# 虚拟滚动

通过设置 useVirtual 为 true，开启列表虚拟滚动

# en-US order=7

# Support Virtual List

You can enable virtual list by set `userVirtual` to `ture`


---


## transfer

# Transfer

-   category: Components
-   family: DataEntry
-   chinese: 穿梭框
-   type: 基本

---

双栏穿梭选择框。

## 何时使用

-   用直观的方式在两栏中移动元素，完成选择行为。
-   需要在多个可选项中进行多选时。
-   比起 Select 和 TreeSelect，穿梭框占据更大的空间，可以展示可选项的更多信息。

## API

### Transfer

| 参数                | 说明                                                                                                                                                                                                               | 类型                                                                                                                                   | 默认值      | 是否必填 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- | ----------- | -------- |
| mode                | 移动选项模式                                                                                                                                                                                                       | 'normal' \| 'simple'                                                                                                                   | 'normal'    |          |
| dataSource          | 数据源                                                                                                                                                                                                             | Array\<TransferDataItem>                                                                                                               | []          |          |
| value               | （用于受控）当前值                                                                                                                                                                                                 | Array\<string>                                                                                                                         | -           |          |
| defaultValue        | （用于非受控）初始值                                                                                                                                                                                               | Array\<string>                                                                                                                         | []          |          |
| onChange            | 值发生改变的时候触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 右面板值<br/>_data_: 右面板数据<br/>_extra_: 额外参数                                                                                 | (value: Array\<string>, data: Array\<TransferDataItem>, extra: ExtraOptions) => void                                                   | -           |          |
| onSelect            | Item 被选中的时候触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_sourceSelectedValue_: 源面板选中的 Item 列表<br/>_targetSelectedValue_: 目标面板选中的 Item 列表<br/>_target_: 触发面板 'source' \| 'target' | (<br/> sourceSelectedValue: Array\<string>,<br/> targetSelectedValue: Array\<string>,<br/> target: 'source' \| 'target'<br/> ) => void | -           |          |
| disabled            | 是否禁用                                                                                                                                                                                                           | boolean                                                                                                                                | false       |          |
| leftDisabled        | 是否禁用左侧面板                                                                                                                                                                                                   | boolean                                                                                                                                | false       |          |
| rightDisabled       | 是否禁用右侧面板                                                                                                                                                                                                   | boolean                                                                                                                                | false       |          |
| itemRender          | 列表项渲染函数<br/><br/>**签名**:<br/>**参数**:<br/>_data_: 数据<br/>**返回值**:<br/>列表项内容                                                                                                                    | (data: TransferDataItem) => React.ReactNode                                                                                            | -           |          |
| showSearch          | 左右面板是否显示搜索框                                                                                                                                                                                             | boolean \| [leftPanel: boolean, rightPanel: boolean]                                                                                   | false       |          |
| searchProps         | 左右面板搜索框配置                                                                                                                                                                                                 | SearchProps \| [leftPanel: SearchProps, rightPanel: SearchProps]                                                                       | -           |          |
| filter              | 自定义搜索函数<br/><br/>**签名**:<br/>**参数**:<br/>_searchedValue_: 搜索框输入的值<br/>_data_: 数据<br/>**返回值**:<br/>是否匹配到                                                                                | (searchedValue: string, data: TransferDataItem) => boolean                                                                             | -           |          |
| onSearch            | 搜索框输入时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_searchedValue_: 搜索框输入的值<br/>_position_: 搜索面板的位置                                                                                     | (searchedValue: string, position: string) => void                                                                                      | -           |          |
| useVirtual          | 是否开启虚拟滚动                                                                                                                                                                                                   | boolean                                                                                                                                | -           |          |
| searchPlaceholder   | 搜索框占位符                                                                                                                                                                                                       | string                                                                                                                                 | -           |          |
| notFoundContent     | 列表为空显示内容                                                                                                                                                                                                   | React.ReactNode \| [leftPanel: React.ReactNode, rightPanel: React.ReactNode]                                                           | 'Not Found' |          |
| titles              | 左右面板标题                                                                                                                                                                                                       | [leftPanel: React.ReactNode, rightPanel: React.ReactNode]                                                                              | []          |          |
| operations          | 向右向左移动按钮显示内容                                                                                                                                                                                           | [leftPanel: React.ReactNode, rightPanel: React.ReactNode]                                                                              | []          |          |
| defaultLeftChecked  | 左面板默认选中值                                                                                                                                                                                                   | Array\<string>                                                                                                                         | []          |          |
| defaultRightChecked | 右面板默认选中值                                                                                                                                                                                                   | Array\<string>                                                                                                                         | []          |          |
| listClassName       | 左右面板列表自定义样式类名                                                                                                                                                                                         | string                                                                                                                                 | -           |          |
| listStyle           | 左右面板列表自定义样式对象                                                                                                                                                                                         | React.CSSProperties                                                                                                                    | -           |          |
| sortable            | 是否允许拖拽排序                                                                                                                                                                                                   | boolean                                                                                                                                | false       |          |
| onSort              | 拖拽排序时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 右面板值<br/>_position_: 拖拽的面板位置，值为：left 或 right                                                                                | (value: Array\<string>, position: PositionType) => void                                                                                | -           |          |
| id                  | 请设置 id 以保证transfer的可访问性                                                                                                                                                                                 | string                                                                                                                                 | -           |          |
| showCheckAll        | 是否显示底部全选 checkbox                                                                                                                                                                                          | boolean                                                                                                                                | true        |          |
| children            | 接收 children 自定义渲染列表                                                                                                                                                                                       | (props: TransferPanelProps) => React.ReactNode                                                                                         | -           |          |

### TransferDataItem

```typescript
export type TransferDataItem = {
    label: string | React.ReactNode;
    value: string;
    title?: string;
    disabled?: boolean;
    children?: TransferDataItem[];
    [key: string]: unknown;
};
```

### PositionType

```typescript
export type PositionType = 'left' | 'right';
```

### DragGapType

```typescript
export type DragGapType = 'before' | 'after';
```

### ExtraOptions

```typescript
export type ExtraOptions = {
    /**
     * 移动的方向，值为'left'或'right'
     * @en Move direction, 'left' or 'right'
     */
    direction: PositionType;
    /**
     * 左面板值
     * @en Data of left panel
     */
    leftValue: string[];
    /**
     * 左面板数据
     * @en Data of left panel
     */
    leftData: TransferDataItem[];
    /**
     * 发生移动的数据
     * @en Moved data
     */
    movedData: TransferDataItem[];
    /**
     * 发生移动的值
     * @en Moved value
     */
    movedValue: string[];
};
```

## 无障碍键盘操作指南

| 按键       | 说明                                              |
| :--------- | :------------------------------------------------ |
| Up Arrow   | 获取当前项的前一项焦点                            |
| Down Arrow | 获取当前项的后一项焦点                            |
| Enter      | 当前列表选中的项移动到另一个列表                  |
| SPACE      | 选择/取消当前项或当前列表选中的项移动到另一个列表 |


---


## tree

# zh-CN order=0

# 基本

最简单的用法，展示可展开，可选中，可勾选，可编辑，可右键，禁用，禁用勾选，默认展开，默认选中，默认勾选等功能。

# en-US order=0

# Basic

the simplest usage: can be expanded, selectable, checkable, editable, can be right-clicked, disabled, disabled-checked, default expanded, selected by default, checked by default, etc.


---


## tree

# zh-CN order=3

# 勾选

通过设置`checkable`为`true`，开启节点勾选，默认情况下，节点的勾选状态受上下级节点的关联，可以通过`checkStrictly`为`false`关闭该关联逻辑。

# en-US order=3

# Parent and child node checked is related

Demo whether parent and child node checked is related.


---


## tree

# zh-CN order=3

# 展开折叠

受控模式展开或折叠节点

# en-US order=3

# Expand and collapse

expand&collapse node on controlled mode


---


## tree

# zh-CN order=2

# 单选与多选

通过设置`multiple`为`true`，支持节点多选。

# en-US order=2

# Single and multiple selection

Demo single and multiple selection.


---


## tree

# zh-CN order=1

# 数据直接生成

使用 dataSource 生成树结构，除设置 `key`, `label`, `children` 属性外，还可传入 `TreeNode` 的其他属性，详细见[TreeNode API](#Tree.Node)，推荐使用该方式生成 Tree 组件。

# en-US order=1

# Render by dataSource

Using the dataSource generate tree structure, in addition to setting the `key`, `label`, and `children` properties, you can pass in other `TreeNode` properties, including selectable, disabled, checked, checkboxDisabled, and isLeaf.


---


## tree

# zh-CN order=9

# 实现拖动

实现节点的拖动逻辑。

# en-US order=9

# Drag

Drag the node inside or around other nodes.


---


## tree

# zh-CN order=6

# 异步加载

点击展开节点之后动态加载数据，常用于通过后端接口获取数据的场景。通过设置 `loadData` 属性开启，通过设置 `isLeaf` 属性，判断节点是否是叶子节点，允许异步加载数据。

# en-US order=6

# Loading data asynchronously

Click node to load data dynamically.


---


## tree

# zh-CN order=5

# 图标

可以设置节点文本前的`icon`图标。

# en-US order=5

# Show Icon

Demo the tree node with icon.


---


## tree

# zh-CN order=4

# 带线样式

使用`showLine`开启节点之间的连接线，用于更清晰地展示节点的层级结构。

# en-US order=4

# Show line

Demo the tree with line.


---


## tree

# zh-CN order=9

# 树节点占满一行

可以通过设置 `isNodeBlock` 为 `true`，来让树节点占满一行，`isNodeBlock` 也可传入一个对象，支持设置 `defaultPaddingLeft`（默认的左内边距）和 `indent` （缩进距离），另外注意 `showLine`  在开启 `isNodeBlock` 时失效。

# en-US order=9

# Tree node is block

You can set `isNodeBlock` to `true` to make the node block. The `isNodeBlock` can also pass in an object. You can set `defaultPaddingLeft` (the default left padding) and `indent`. Also note `isNodeBlock` will not work if you set `showLine` to true.


---


## tree

# zh-CN order=9&debug=true

# 平铺叶子节点

当最后一级都是叶子节点时，平铺展示

# en-US order=9&debug=true

# Tile leaf nodes

When the last level is all leaf nodes, the tiling display.


---


## tree

# zh-CN order=8

# 实现搜索

组合 `Search` 组件，实现 `Tree` 组件的搜索。通过 `ref` 获取 `Tree` 实例，可调用 `scrollFilterNodeIntoView` 方法实现将匹配到的第一个节点滚动到可视区域。

# en-US order=8

# Searchable

Demos the searchable tree. Use `ref` to get the tree instance, and call `scrollFilterNodeIntoView` to scroll to the first matched node.


---


## tree

# zh-CN order=7

# 虚拟滚动

当树的节点数比较多的时候，设置虚拟滚动提高性能，注意设置高度，且允许滚动。

# en-US order=7

# Virtual Tree

Setting useVirtual property to improve performance when there are many nodes in the tree,pay attention to set height and allow to scroll.


---


## tree

# Tree

-   category: Components
-   family: DataDisplay
-   chinese: 树形控件
-   type: 基本

---

用于展示具有层级结构的数据。

## 何时使用

`Tree`组件适用于大量、具有层级关系的数据展示场景中，并且利用组件的展开收起和关联选中等交互可以方便地对数据进行操作处理。

## API

### Tree

| 参数                | 说明                                                                                                                                                                              | 类型                                                                                                                                                                                                                                                          | 默认值      | 是否必填 | 支持版本 |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | -------- | -------- |
| children            | 树节点                                                                                                                                                                            | React.ReactNode                                                                                                                                                                                                                                               | -           |          | -        |
| dataSource          | 数据源，该属性优先级高于 children                                                                                                                                                 | TreeDataType[]                                                                                                                                                                                                                                                | -           |          | -        |
| showLine            | 是否显示树的线                                                                                                                                                                    | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| selectable          | 是否支持选中节点                                                                                                                                                                  | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| selectedKeys        | （用于受控）当前选中节点 key 的数组                                                                                                                                               | string[]                                                                                                                                                                                                                                                      | -           |          | -        |
| defaultSelectedKeys | （用于非受控）默认选中节点 key 的数组                                                                                                                                             | string[]                                                                                                                                                                                                                                                      | []          |          | -        |
| onSelect            | 选中或取消选中节点时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_selectedKeys_: 选中节点key的数组<br/>_extra_: 额外参数<br/>**返回值**:<br/>空                            | (<br/> selectedKeys: string[],<br/> extra: {<br/> selectedNodes: Array\<NodeInstance>;<br/> node: NodeInstance;<br/> selected: boolean;<br/> event: React.KeyboardEvent \| React.MouseEvent;<br/> }<br/> ) => void                                            | () =\> \{\} |          | -        |
| multiple            | 是否支持多选                                                                                                                                                                      | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| checkable           | 是否支持勾选节点的复选框                                                                                                                                                          | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| checkedKeys         | （用于受控）当前勾选复选框节点 key 的数组或 `{checked: Array, indeterminate: Array}` 的对象                                                                                       | \| {<br/> checked: string[];<br/> indeterminate: string[];<br/> }<br/> \| string[]                                                                                                                                                                            | -           |          | -        |
| defaultCheckedKeys  | （用于非受控）默认勾选复选框节点 key 的数组                                                                                                                                       | \| {<br/> checked: string[];<br/> indeterminate: string[];<br/> }<br/> \| string[]                                                                                                                                                                            | []          |          | -        |
| checkStrictly       | 勾选节点复选框是否完全受控（父子节点选中状态不再关联）                                                                                                                            | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| checkedStrategy     | 定义选中时回填的方式                                                                                                                                                              | 'all' \| 'parent' \| 'child'                                                                                                                                                                                                                                  | 'all'       |          | -        |
| onCheck             | 勾选或取消勾选复选框时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_checkedKeys_: 勾选复选框节点key的数组<br/>_extra_: 额外参数<br/>**返回值**:<br/>空                     | (<br/> checkedKeys: string[],<br/> extra: {<br/> checkedNodes: Array\<NodeInstance>;<br/> checkedNodesPositions: Array\<NodeInstance>;<br/> indeterminateKeys: string[];<br/> node: NodeInstance;<br/> checked: boolean;<br/> key: Key;<br/> }<br/> ) => void | () =\> \{\} |          | -        |
| expandedKeys        | （用于受控）当前展开的节点 key 的数组                                                                                                                                             | string[]                                                                                                                                                                                                                                                      | -           |          | -        |
| defaultExpandedKeys | （用于非受控）默认展开的节点 key 的数组                                                                                                                                           | string[]                                                                                                                                                                                                                                                      | []          |          | -        |
| defaultExpandAll    | 是否默认展开所有节点                                                                                                                                                              | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| autoExpandParent    | 是否自动展开父节点                                                                                                                                                                | boolean                                                                                                                                                                                                                                                       | true        |          | -        |
| onExpand            | 展开或收起节点时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_expandedKeys_: 展开节点key的数组<br/>_extra_: 额外参数<br/>**返回值**:<br/>空                                | (<br/> expandedKeys: string[],<br/> extra: {<br/> node: NodeInstance;<br/> expanded: boolean;<br/> }<br/> ) => void                                                                                                                                           | () =\> \{\} |          | -        |
| editable            | 是否支持编辑节点内容                                                                                                                                                              | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| onEditFinish        | 编辑节点内容完成时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_key_: 编辑节点 key<br/>_label_: 编辑节点完成时节点的文本<br/>_node_: 当前编辑的节点<br/>**返回值**:<br/>空 | (key: Key, label: string, node: NodeInstance) => void                                                                                                                                                                                                         | () =\> \{\} |          | -        |
| draggable           | 是否支持拖拽节点                                                                                                                                                                  | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| onDragStart         | 开始拖拽节点时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>空                                                                         | (info: {<br/> event: React.MouseEvent;<br/> node: NodeInstance;<br/> expandedKeys: string[];<br/> }) => void                                                                                                                                                  | () =\> \{\} |          | -        |
| onDragEnter         | 拖拽节点进入目标节点时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>空                                                                 | (info: {<br/> event: React.MouseEvent;<br/> node: NodeInstance;<br/> expandedKeys: Array\<string>;<br/> }) => void                                                                                                                                            | () =\> \{\} |          | -        |
| onDragOver          | 拖拽节点在目标节点上移动的时候触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>空                                                         | (info: { event: React.MouseEvent; node: NodeInstance }) => void                                                                                                                                                                                               | () =\> \{\} |          | -        |
| onDragLeave         | 拖拽节点离开目标节点时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>空                                                                 | (info: { event: React.MouseEvent; node: NodeInstance }) => void                                                                                                                                                                                               | () =\> \{\} |          | -        |
| onDragEnd           | 拖拽节点拖拽结束时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>空                                                                     | (info: { event: React.MouseEvent; node: NodeInstance }) => void                                                                                                                                                                                               | () =\> \{\} |          | -        |
| onDrop              | 拖拽节点放入目标节点内或前后触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>空                                                           | (info: {<br/> event: React.MouseEvent;<br/> node: NodeInstance;<br/> dragNode: NodeInstance;<br/> dragNodesKeys: Array\<string>;<br/> dropPosition: number;<br/> }) => void                                                                                   | () =\> \{\} |          | -        |
| canDrop             | 节点是否可被作为拖拽的目标节点<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>是否可以被当作目标节点                                                   | (info: {<br/> event?: React.MouseEvent;<br/> node: NodeInstance;<br/> dragNode: NodeInstance;<br/> dragNodesKeys: Array\<string>;<br/> dropPosition: number;<br/> }) => boolean                                                                               | () =\> \{\} |          | -        |
| loadData            | 异步加载数据的函数<br/><br/>**签名**:<br/>**参数**:<br/>_node_: 被点击展开的节点                                                                                                  | (node: NodeInstance) => Promise\<unknown>                                                                                                                                                                                                                     | -           |          | -        |
| filterTreeNode      | 按需筛选高亮节点<br/><br/>**签名**:<br/>**参数**:<br/>_node_: 待筛选的节点<br/>**返回值**:<br/>是否被筛选中                                                                       | (node: NodeInstance) => boolean                                                                                                                                                                                                                               | -           |          | -        |
| onRightClick        | 右键点击节点时触发的回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_info_: 额外参数<br/>**返回值**:<br/>空                                                                         | (info: { event: React.MouseEvent; node: NodeInstance }) => void                                                                                                                                                                                               | () =\> \{\} |          | -        |
| isLabelBlock        | 设置节点是否占满剩余空间，一般用于统一在各节点右侧添加元素(借助 flex 实现，暂时只支持 ie10+)                                                                                      | boolean                                                                                                                                                                                                                                                       | false       |          | -        |
| isNodeBlock         | 设置节点是否占满一行                                                                                                                                                              | boolean \| Record\<string, unknown>                                                                                                                                                                                                                           | false       |          | -        |
| animation           | 是否开启展开收起动画                                                                                                                                                              | boolean                                                                                                                                                                                                                                                       | true        |          | -        |
| focusedKey          | 当前获得焦点的子菜单或菜单项 key 值                                                                                                                                               | Key                                                                                                                                                                                                                                                           | -           |          | -        |
| renderChildNodes    | 渲染子节点<br/><br/>**签名**:<br/>**参数**:<br/>_nodes_: 所有的子节点<br/>**返回值**:<br/>子节点                                                                                  | (nodes: NodeElement[]) => React.ReactNode                                                                                                                                                                                                                     | -           |          | -        |
| labelRender         | 渲染单个子节点<br/><br/>**签名**:<br/>**参数**:<br/>_node_: 节点数据<br/>**返回值**:<br/>返回节点                                                                                 | (node: Record\<string, unknown>) => React.ReactNode                                                                                                                                                                                                           | -           |          | 1.25     |
| immutable           | 是否是不可变数据                                                                                                                                                                  | boolean                                                                                                                                                                                                                                                       | false       |          | 1.23     |
| useVirtual          | 是否开启虚拟滚动                                                                                                                                                                  | boolean                                                                                                                                                                                                                                                       | false       |          | -        |

### Tree.Node

| 参数             | 说明                                           | 类型            | 默认值 | 是否必填 |
| ---------------- | ---------------------------------------------- | --------------- | ------ | -------- |
| children         | 树节点                                         | React.ReactNode | -      |          |
| label            | 节点文本内容                                   | React.ReactNode | '--    |          |
| selectable       | 单独设置是否支持选中，覆盖 Tree 的 selectable  | boolean         | -      |          |
| checkable        | 单独设置是否出现复选框，覆盖 Tree 的 checkable | boolean         | -      |          |
| editable         | 单独设置是否支持编辑，覆盖 Tree 的 editable    | boolean         | -      |          |
| draggable        | 单独设置是否支持拖拽，覆盖 Tree 的 draggable   | boolean         | -      |          |
| disabled         | 是否禁止节点响应                               | boolean         | false  |          |
| checkboxDisabled | 是否禁止勾选节点复选框                         | boolean         | false  |          |
| isLeaf           | 是否是叶子节点，设置loadData时生效             | boolean         | -      |          |


---


## tree-select

# zh-CN order=7

# 无障碍支持

通过`aria-labelledby`对组件进行描述。关于键盘操作请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=7

# Accessibility

Description of components is through `aria-labelledby`. Please refer to `ARIA and KeyBoard` for keyboard operation.


---


## tree-select

# zh-CN order=0

# 基本

最简单的单选用法。

# en-US order=0

# Basic

The simplest single select usage.


---


## tree-select

# zh-CN order=3

# 勾选

通过设置 `treeCheckable`，开启 `Tree` 组件的勾选功能，注意，此时组件处于可多选状态，`multiple` 属性无效。

# en-US order=3

# Checkbox

Demo the multiple select usage.


---


## tree-select

# zh-CN order=4

# 受控

展示树选择受控的用法。

# en-US order=4

# Control

Demo the control select usage.


---


## tree-select

# zh-CN order=1

# 数据直接生成

使用 dataSource 生成树结构，除设置 `key`, `label`, `children` 属性外，还可传入 `TreeNode` 的其他属性，详细见[TreeNode API](../tree#Tree.Node)，推荐使用该方式生成 Tree 组件。

# en-US order=1

# Render by dataSource

Using the dataSource generate tree structure, in addition to setting the key, label, and children properties, you can pass in other TreeNode properties, including selectable, disabled, checked, checkboxDisabled, and isLeaf. It is recommended to use `dataSource` instead of manually generate a tree, which is easier to use and better performance.


---


## tree-select

# zh-CN order=4

# 单行显示

支持单行显示。

# en-US order=5

# inline

single line display


---


## tree-select

# zh-CN order=5

# value 不存在

通过设置 `preserveNonExistentValue`，可以让 value 在 dataSource 中不存在时仍然显示

# en-US order=0

# non-existent-value

display value even though value not exist in dataSource


---


## tree-select

# zh-CN order=5&debug=true

# 异步搜索

展示树选择异步搜索的用法。

# en-US order=5&debug=true

# Search usage

Demo the search pro usage.


---


## tree-select

# zh-CN order=4

# 搜索用法

展示树选择的搜索用法。

# en-US order=4

# Search usage

Demo the search usage.


---


## tree-select

# zh-CN order=2

# 单选与多选

展示单选与多选的用法。

# en-US order=2

# Single and multiple selection

Demo single and multiple selection.


---


## tree-select

# zh-CN order=4

# 全路径展示

通过valueRender支持下拉框展示全路径。

# en-US order=4

# Full path display

Full path display at select by valueRender


---


## tree-select

# zh-CN order=8

# 对象数据

`useDetailValue` 把 `value`、`defaultValue`、`onChange 第一个参数`从字符串变成对象

# en-US order=8

# useDetailValue

`useDetailValue` change `value`、`defaultValue`、`first arg of onChange` from string to object


---


## tree-select

# zh-CN order=6

# 虚拟滚动

当树的节点数比较多的时候，设置虚拟滚动提高性能。

# en-US order=6

# Virtual Tree

Setting useVirtual property to improve performance when there are many nodes in the tree.


---


## tree-select

# TreeSelect

-   category: Components
-   family: DataEntry
-   chinese: 树型选择控件
-   type: 基本

---

树型选择控件。

## 何时使用

类似 `Select` 的选择控件，可选择的数据结构是一个树形结构时，可以使用 `TreeSelect`，例如公司层级、学科系统、分类目录等等。

## API

### TreeSelect

| 参数                     | 说明                                                                                                                                                                                                                                                   | 类型                                                                                                           | 默认值                                | 是否必填 | 支持版本 |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------- | ------------------------------------- | -------- | -------- |
| children                 | 树节点                                                                                                                                                                                                                                                 | React.ReactNode                                                                                                | -                                     |          | -        |
| size                     | 选择框大小                                                                                                                                                                                                                                             | 'small' \| 'medium' \| 'large'                                                                                 | 'medium'                              |          | -        |
| placeholder              | 选择框占位符                                                                                                                                                                                                                                           | string                                                                                                         | -                                     |          | -        |
| disabled                 | 是否禁用                                                                                                                                                                                                                                               | boolean                                                                                                        | false                                 |          | -        |
| hasArrow                 | 是否有下拉箭头                                                                                                                                                                                                                                         | boolean                                                                                                        | true                                  |          | -        |
| hasBorder                | 是否有边框                                                                                                                                                                                                                                             | boolean                                                                                                        | true                                  |          | -        |
| hasClear                 | 是否有清空按钮                                                                                                                                                                                                                                         | boolean                                                                                                        | true                                  |          | -        |
| label                    | 自定义内联 label                                                                                                                                                                                                                                       | React.ReactNode                                                                                                | -                                     |          | -        |
| readOnly                 | 是否只读，只读模式下可以展开弹层但不能选择                                                                                                                                                                                                             | boolean                                                                                                        | -                                     |          | -        |
| autoWidth                | 下拉框是否与选择器对齐                                                                                                                                                                                                                                 | boolean                                                                                                        | true                                  |          | -        |
| dataSource               | 数据源，该属性优先级高于 children                                                                                                                                                                                                                      | DataSourceItem[]                                                                                               | -                                     |          | -        |
| value                    | （受控）当前值                                                                                                                                                                                                                                         | DataSourceItem[] \| DataSourceItem                                                                             | -                                     |          | -        |
| defaultValue             | （非受控）默认值                                                                                                                                                                                                                                       | SelectProps['defaultValue']                                                                                    | null                                  |          | -        |
| preserveNonExistentValue | value/defaultValue 在 dataSource 中不存在时，是否展示                                                                                                                                                                                                  | boolean                                                                                                        | false                                 |          | 1.25     |
| onChange                 | 选中值改变时触发的回调函数                                                                                                                                                                                                                             | (<br/> value: DataSourceItem[] \| DataSourceItem,<br/> data: ObjectItem[] \| ObjectItem \| null<br/> ) => void | () =\> \{\}                           |          | -        |
| tagInline                | 是否一行显示，仅在 multiple 和 treeCheckable 为 true 时生效                                                                                                                                                                                            | boolean                                                                                                        | false                                 |          | 1.25     |
| maxTagPlaceholder        | 隐藏多余 tag 时显示的内容，在 tagInline 生效时起作用<br/><br/>**签名**:<br/>**参数**:<br/>_selectedValues_: 当前已选中的元素<br/>_totalValues_: 总待选元素，treeCheckedStrategy = 'parent' 时为 undefined<br/>**返回值**:<br/>ReactNode \| HTMLElement | (<br/> selectedValues: ObjectItem[],<br/> totalValues?: ObjectItem[]<br/> ) => React.ReactNode \| HTMLElement  | -                                     |          | 1.25     |
| autoClearSearch          | 是否自动清除 searchValue                                                                                                                                                                                                                               | boolean                                                                                                        | true                                  |          | 1.26     |
| showSearch               | 是否显示搜索框                                                                                                                                                                                                                                         | boolean                                                                                                        | false                                 |          | -        |
| onSearch                 | 在搜索框中输入时触发的回调函数                                                                                                                                                                                                                         | (keyword: string) => void                                                                                      | () =\> \{\}                           |          | -        |
| notFoundContent          | 无数据时显示内容                                                                                                                                                                                                                                       | React.ReactNode                                                                                                | 'Not Found'                           |          | -        |
| multiple                 | 是否支持多选                                                                                                                                                                                                                                           | boolean                                                                                                        | false                                 |          | -        |
| treeCheckable            | 下拉框中的树是否支持勾选节点的复选框                                                                                                                                                                                                                   | boolean                                                                                                        | false                                 |          | -        |
| treeCheckStrictly        | 下拉框中的树勾选节点复选框是否完全受控（父子节点选中状态不再关联）                                                                                                                                                                                     | boolean                                                                                                        | false                                 |          | -        |
| treeCheckedStrategy      | 定义选中时回填的方式                                                                                                                                                                                                                                   | 'all' \| 'parent' \| 'child'                                                                                   | 'parent'                              |          | -        |
| treeDefaultExpandAll     | 下拉框中的树是否默认展开所有节点                                                                                                                                                                                                                       | boolean                                                                                                        | false                                 |          | -        |
| treeDefaultExpandedKeys  | 下拉框中的树默认展开节点key的数组                                                                                                                                                                                                                      | Array\<Key>                                                                                                    | []                                    |          | -        |
| treeLoadData             | 下拉框中的树异步加载数据的函数，使用请参考[Tree的异步加载数据Demo](https://fusion.design/pc/component/basic/tree#%E5%BC%82%E6%AD%A5%E5%8A%A0%E8%BD%BD%E6%95%B0%E6%8D%AE)                                                                               | TreeProps['loadData']                                                                                          | -                                     |          | -        |
| treeProps                | 透传到 Tree 的属性对象                                                                                                                                                                                                                                 | TreeProps                                                                                                      | \{\}                                  |          | -        |
| defaultVisible           | 初始下拉框是否显示                                                                                                                                                                                                                                     | boolean                                                                                                        | false                                 |          | -        |
| visible                  | 当前下拉框是否显示                                                                                                                                                                                                                                     | boolean                                                                                                        | -                                     |          | -        |
| onVisibleChange          | 下拉框显示或关闭时触发事件的回调函数                                                                                                                                                                                                                   | (visible: boolean, type: string) => void                                                                       | () =\> \{\}                           |          | -        |
| popupStyle               | 下拉框自定义样式对象                                                                                                                                                                                                                                   | React.CSSProperties                                                                                            | -                                     |          | -        |
| popupClassName           | 下拉框样式自定义类名                                                                                                                                                                                                                                   | string                                                                                                         | -                                     |          | -        |
| popupContainer           | 下拉框挂载的容器节点                                                                                                                                                                                                                                   | string \| HTMLElement \| ((target: HTMLElement) => HTMLElement)                                                | -                                     |          | -        |
| popupProps               | 透传到 Popup 的属性对象                                                                                                                                                                                                                                | PopupProps                                                                                                     | -                                     |          | -        |
| followTrigger            | 是否跟随滚动                                                                                                                                                                                                                                           | boolean                                                                                                        | -                                     |          | -        |
| isPreview                | 是否为预览态                                                                                                                                                                                                                                           | boolean                                                                                                        | -                                     |          | -        |
| renderPreview            | 预览态模式下渲染的内容                                                                                                                                                                                                                                 | (data: ObjectItem[], props: TreeSelectProps) => React.ReactNode                                                | -                                     |          | -        |
| useVirtual               | 是否开启虚拟滚动                                                                                                                                                                                                                                       | boolean                                                                                                        | false                                 |          | -        |
| filterLocal              | 是否关闭本地搜索                                                                                                                                                                                                                                       | boolean                                                                                                        | true                                  |          | -        |
| immutable                | 是否是不可变数据                                                                                                                                                                                                                                       | boolean                                                                                                        | -                                     |          | 1.23     |
| clickToCheck             | 点击文本是否可以勾选                                                                                                                                                                                                                                   | boolean                                                                                                        | false                                 |          | -        |
| valueRender              | 渲染 Select 区域展现内容的方法<br/><br/>**签名**:<br/>**参数**:<br/>_item_: 渲染项<br/>_itemPaths_: 渲染项在dataSource内的路径<br/>**返回值**:<br/>ReactNode - 展现内容                                                                                | (item: TreeSelectState['\_k2n'][Key], itemPaths: ObjectItem[]) => React.ReactNode                              | (item) =\> item.label \|\| item.value |          | -        |

<!-- api-extra-start -->

### TreeSelect.Node

| 参数             | 说明                                           | 类型      | 默认值 |
| ---------------- | ---------------------------------------------- | --------- | ------ |
| children         | 树节点                                         | ReactNode | -      |
| label            | 节点文本内容                                   | ReactNode | '---'  |
| selectable       | 单独设置是否支持选中，覆盖 Tree 的 selectable  | Boolean   | -      |
| checkable        | 单独设置是否出现复选框，覆盖 Tree 的 checkable | Boolean   | -      |
| editable         | 单独设置是否支持编辑，覆盖 Tree 的 editable    | Boolean   | -      |
| draggable        | 单独设置是否支持拖拽，覆盖 Tree 的 draggable   | Boolean   | -      |
| disabled         | 是否禁止节点响应                               | Boolean   | false  |
| checkboxDisabled | 是否禁止勾选节点复选框                         | Boolean   | false  |
| isLeaf           | 是否是叶子节点，设置 loadData 时生效           | Boolean   | false  |

### dataSource 数据结构

```js
const dataSource = [
    {
        label: '服装',
        value: '1',
        key: '1',
        selectable: false,
        children: [
            {
                label: '男装',
                value: '2',
                key: '2',
                children: [
                    {
                        label: '外套',
                        value: '4',
                        key: '4',
                        disableCheckbox: true,
                    },
                    {
                        label: '夹克',
                        value: '5',
                        key: '5',
                        disabled: true,
                    },
                ],
            },
            {
                label: '女装',
                value: '3',
                key: '3',
                children: [
                    {
                        label: '裙子',
                        value: '6',
                        key: '6',
                    },
                ],
            },
        ],
    },
];
```

如果不传入 key，TreeSelect 会使用内部计算出来的位置字符串作为 key 值，如果你想指定诸如 treeDefaultExpandedKeys 这样的属性，请传入自定义的 key 值，让它和 value 是一个值，是一个很好的办法。

<!-- api-extra-end -->

## 无障碍键盘操作指南

| 按键        | 说明                                   |
| :---------- | :------------------------------------- |
| Enter       | 打开选择树或选择某一项                 |
| Up Arrow    | 获取同级当前项前一项焦点               |
| Down Arrow  | 获取同级当前项后一项焦点               |
| Right Arrow | 打开当前元素的下一级子树并聚焦到第一项 |
| Left Arrow  | 返回到当前元素的父节点并关闭当前子树   |


---


## typography

# zh-CN order=0

# 基本

最简单的用法。

# en-US order=0

# basic

simple usage


---


## typography

# zh-CN order=3

# 段落

一段文字

# en-US order=3

# Paragraph

A paragraph of text


---


## typography

# zh-CN order=2

# 文本

内置不同样式的文本。

# en-US order=2

# Text

Provides multiple types of text.


---


## typography

# zh-CN order=1

# 标题

展示不同级别的标题。

# en-US order=1

# Title

Display title in different level.


---


## typography

# Typography

-   category: Components
-   family: General
-   chinese: 排版
-   type: 基本
-   version: 1.18

---

文本的基本格式。

## 何时使用

-   当需要展示标题、段落、列表内容时使用，如文章/博客/日志的文本样式。

## API

### Typography

继承 Typography.Text API

| 参数      | 说明         | 类型                                  | 默认值  | 是否必填 |
| --------- | ------------ | ------------------------------------- | ------- | -------- |
| component | 设置标签类型 | string \| React.JSX.IntrinsicElements | article |          |

### Typography.Title

分为 H1, H2, H3, H4, H5, H6 不同的组件，表示不同层级，继承 Typography.Text API

### Typography.Paragraph

继承 Typography.Text 的 API

| 参数      | 说明         | 类型                                  | 默认值 | 是否必填 |
| --------- | ------------ | ------------------------------------- | ------ | -------- |
| component | 设置标签类型 | string \| React.JSX.IntrinsicElements | p      |          |

### Typography.Text

| 参数      | 说明                | 类型                                  | 默认值 | 是否必填 |
| --------- | ------------------- | ------------------------------------- | ------ | -------- |
| delete    | 添加删除线样式      | boolean                               | false  |          |
| mark      | 添加标记样式        | boolean                               | false  |          |
| underline | 添加下划线样式      | boolean                               | false  |          |
| strong    | 是否加粗            | boolean                               | false  |          |
| code      | 添加代码样式        | boolean                               | false  |          |
| component | 设置标签类型        | string \| React.JSX.IntrinsicElements | span   |          |
| rtl       | 是否以 rtl 模式展示 | boolean                               | false  |          |


---


## upload

# zh-CN order=16

# 无障碍支持

请参考[#无障碍键盘操作指南](#无障碍键盘操作指南)。

# en-US order=16

# Accessibility

Please refer to `ARIA and KeyBoard`.


---


## upload

# zh-CN order=12

# 文件校验

afterSelect仅在 autoUpload=false 的时候生效
autoUpload=true时,可以使用beforeUpload完全可以替代该功能.

# en-US order=5

# Submit Upload

afterSelect only works when autoUpload=false and it can be completely replace by beforeUpload method when autoUpload=true

Click a submit button to upload


---


## upload

# zh-CN order=0

# 文件上传

上传按钮根据自己传入的内容而定

提醒: `https://www.easy-mock.com/mock/5b713974309d0d7d107a74a3/alifd/upload` 接口:

> 1. 该接口仅作为测试使用,业务请勿使用

> 2. 该接口仅支持图片上传,其他文件类型接口请自备

# en-US order=0

# Basic Usage

custom action button by your self

Waring: `https://www.easy-mock.com/mock/5b713974309d0d7d107a74a3/alifd/upload` API:

> 1. only for test & develop, Never Use in production enviroments

> 2. only support upload images


---


## upload

# zh-CN order=8

# 上传前预处理

使用 `beforeUpload` 在上传前确认有计划确实是否需要上传或者拦截, 返回 false 或者 Promise.reject 都会中断上传。

# en-US order=8

# BeforeUpload

use `beforeUpload` to control upload


---


## upload

# zh-CN order=3

# 卡片

# en-US order=3

# Card


---


## upload

# zh-CN order=10

# 裁剪上传

通过转换 dataURL to Blob to File, 构造文件对象

# en-US order=10

# Crop

transfor dataURL to Blob to File


---


## upload

# zh-CN order=4

# 添加上传参数

通过 data 控制自定义参数, 可以是一个 对象 或者 函数

# en-US order=4

# Custom Upload Params

using `data` param to put custom params in. can be a object or function


---


## upload

# zh-CN order=6

# 文件夹上传

支持上传一个文件夹里的所有文件。

# en-US order=6

# directory upload

support upload a directory


---


## upload

# zh-CN order=4

# 拖拽上传

# en-US order=4

# Drag to Upload


---


## upload

# zh-CN order=8

# 额外内容

# en-US order=8

# Extra


---


## upload

# zh-CN order=2

# 图片列表

# en-US order=2

# Image List


---


## upload

# zh-CN order=6

# 个数限制

# en-US order=6

# limit file numbers


---


## upload

# zh-CN order=6

# 文件大小、长宽限制

设置图片最大宽度为 1200，最大占据磁盘空间大小为2M。思路是在 `beforeUpload` 这个阶段，获取到文件对象，判断文件对象是否符合要求。（注意IE9不支持File这个浏览器原生对象）

# en-US order=6

# size limit

set max width to 1200


---


## upload

# zh-CN order=10

# oss 上传

需要先从后端获取 host/OSSAccessKeyId/policy/signature/key 参数，修改action和data，再利用upload能力上传。

因为 demo 中的 action 为 oss 测试地址，不支持直接上传，所以控制台会报`Access-Control-Allow-Origin`的错误。

真实环境中需要自己在 oss 服务中配置下 `Access-Control-Allow-Origin` 的域名白名单，如果直接设置为 `*` ，则需要设置 `withCredentials=false`，否则依然有跨域报错，<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin#directives" target="_blank">详细见</a>)。

# en-US order=10

# oss upload

get host/OSSAccessKeyId/policy/signature/key by ajax，then modify action/data

If you want to allow credentials then your `Access-Control-Allow-Origin` must not use `*`.


---


## upload

# zh-CN order=5

# 粘贴上传

# en-US order=5

# paste to upload


---


## upload

# zh-CN order=5

# 不自动上传

通过按钮点击提交上传

# en-US order=5

# Upload after submit

Click a submit button to upload


---


## upload

# zh-CN order=1

# 文字列表

# en-US order=1

# Submit Upload


---


## upload

# zh-CN order=6&debug=true

# 内容回填

# en-US order=6

# Content fill


---


## upload

# Upload

-   category: Components
-   family: DataEntry
-   chinese: 上传组件
-   cols: 1
-   type: 表单

---

文件选择上传和拖拽上传控件。

## 何时使用

用户根据提示将自己本地的相应信息(包含本地和云储存)上传到网站，上传组件可以帮助用户对上传过程和上传结果有预期，并可以更改或撤销上传行为。

参考文章: <a href="https://zhuanlan.zhihu.com/p/56684600" target="_blank">Upload 组件的设计思想</a> & <a href="https://zhuanlan.zhihu.com/p/59483736" target="_blank">Fusion Upload组件对接阿里云OSS/七牛/又拍</a>。

## 如何使用

### 跨域问题

有些服务不支持 `X-Requested-With: XMLHttpRequest` 这个请求头导致不能跨域，可以通过设置 `<Upload headers={{'X-Requested-With':null}}>` 来解决。

### IE9兼容性

-   ie9 下用因为使用 iframe 作为无刷新上传方案，必须保证表单页面的域名和上传的服务器端的域名相同。
-   ie9 下服务器端返回数据需要设置头部 `context-type` 为 `text/html`，不要设置为 `application/json`
-   如果只是一级域名相同（`taobao.com` 为一级域名 `shop.taobao.com` 为二级域名），可以通过降域的方式实现跨域上传。

假设你表单页面的域是：shop.taobao.com，而上传的服务器端路径却是 upload.taobao.com。服务端返回必须带额外script标签。
iframe上传会额外传递参数 `_documentDomain` 方便你设置域名。

```jsx
  <script>document.domain="taobao.com";</script>
  {
    "status":1,
    "type":"ajax",
    "name":"54.png",
    "url":".\/files\/54.png"
    }
```

## API

### Upload

| 参数              | 说明                                                                                                                                                                                                                                               | 类型                                                                                                   | 默认值    | 是否必填 | 支持版本 |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | --------- | -------- | -------- |
| action            | 上传的地址                                                                                                                                                                                                                                         | string                                                                                                 | -         |          | -        |
| shape             | 上传按钮形状                                                                                                                                                                                                                                       | 'card'                                                                                                 | -         |          | -        |
| accept            | 接受上传的文件类型 (image/png, image/jpg, .doc, .ppt) 详见 [input accept attribute](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-accept)                                                                                   | string                                                                                                 | -         |          | -        |
| data              | 上传额外传参                                                                                                                                                                                                                                       | \| { [key: string]: string \| Blob }<br/> \| ((file: UploadFile) => { [key: string]: string \| Blob }) | -         |          | -        |
| headers           | 设置上传的请求头部                                                                                                                                                                                                                                 | {<br/> 'X-Requested-With'?: string \| undefined;<br/> [key: string]: unknown;<br/> }                   | -         |          | -        |
| withCredentials   | 是否允许请求携带 cookie                                                                                                                                                                                                                            | boolean                                                                                                | true      |          | -        |
| beforeUpload      | 可选参数，详见 [beforeUpload](#beforeUpload)<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 所有文件<br/>_options_: 参数                                                                                                                             | (file: UploadFile, options: BeforeUploadOption) => boolean \| object \| unknown                        | func.noop |          | -        |
| onProgress        | 上传中                                                                                                                                                                                                                                             | (file: ObjectFile[], e: ObjectFile) => void                                                            | func.noop |          | -        |
| onSuccess         | 可选参数，上传成功回调函数，参数为请求下响应信息以及文件<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 文件<br/>_value_: 值                                                                                                                         | (file: ObjectFile, value?: ObjectFile[]) => void                                                       | func.noop |          | -        |
| onError           | 可选参数，上传失败回调函数，参数为上传失败的信息、响应信息以及文件<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 出错的文件<br/>_value_: 当前值                                                                                                     | (file: ObjectFile, value: ObjectFile[]) => void                                                        | func.noop |          | -        |
| children          | 子元素                                                                                                                                                                                                                                             | ReactNode                                                                                              | -         |          | -        |
| timeout           | 设置上传超时，单位 ms                                                                                                                                                                                                                              | number                                                                                                 | -         |          | -        |
| method            | 上传方法                                                                                                                                                                                                                                           | 'post' \| 'put' \| 'POST' \| 'PUT'                                                                     | 'post'    |          | -        |
| request           | 自定义上传方法<br/><br/>**签名**:<br/>**参数**:<br/>_option_: 参数<br/>**返回值**:<br/>- 返回值                                                                                                                                                    | (option: object) => object                                                                             | -         |          | -        |
| name              | 文件名字段                                                                                                                                                                                                                                         | string                                                                                                 | -         |          | -        |
| onSelect          | 选择文件回调                                                                                                                                                                                                                                       | (uploadFiles: Array\<unknown>, value: Array\<unknown>) => void                                         | func.noop |          | -        |
| onDrop            | 放文件                                                                                                                                                                                                                                             | (files: UploadFile[]) => void                                                                          | func.noop |          | -        |
| value             | 文件列表                                                                                                                                                                                                                                           | Array\<ObjectFile> \| ObjectFile                                                                       | -         |          | -        |
| defaultValue      | 默认文件列表                                                                                                                                                                                                                                       | Array\<ObjectFile> \| ObjectFile                                                                       | -         |          | -        |
| listType          | 上传列表的样式                                                                                                                                                                                                                                     | ListType                                                                                               | -         |          | -        |
| formatter         | 数据格式化函数，配合自定义 action 使用，参数为服务器的响应数据，详见 [formatter](#formater)<br/><br/>**签名**:<br/>**参数**:<br/>_response_: 返回<br/>_file_: 文件对象                                                                             | (response: UploadResponse, file: UploadFile) => UploadResponse                                         | -         |          | -        |
| limit             | 最大文件上传个数                                                                                                                                                                                                                                   | number                                                                                                 | Infinity  |          | -        |
| dragable          | 可选参数，是否支持拖拽上传，`ie10+` 支持。                                                                                                                                                                                                         | boolean                                                                                                | -         |          | -        |
| useDataURL        | 可选参数，是否本地预览                                                                                                                                                                                                                             | boolean                                                                                                | -         |          | -        |
| disabled          | 可选参数，是否禁用上传功能                                                                                                                                                                                                                         | boolean                                                                                                | -         |          | -        |
| onChange          | 上传文件改变时的状态<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 所有文件<br/>_file_: 文件对象                                                                                                                                                   | (value: ObjectFile[], file: ObjectFile \| ObjectFile[]) => void                                        | func.noop |          | -        |
| afterSelect       | 可选参数，用于校验文件，afterSelect 仅在 autoUpload=false 的时候生效，autoUpload=true 时，可以使用 beforeUpload 完全可以替代该功能。<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 文件<br/>**返回值**:<br/>- 返回 false 会阻止上传，其他则表示正常 | (file: ObjectFile) => boolean \| Promise\<void>                                                        | func.noop |          | -        |
| onRemove          | 移除文件回调函数<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 文件<br/>**返回值**:<br/>- 返回 false、Promise.resolve(false)、Promise.reject() 将阻止文件删除                                                                                       | (file: object) => void                                                                                 | func.noop |          | -        |
| autoUpload        | 自动上传                                                                                                                                                                                                                                           | boolean                                                                                                | true      |          | -        |
| progressProps     | 透传给 Progress props                                                                                                                                                                                                                              | ProgressProps                                                                                          | -         |          | -        |
| isPreview         | 是否为预览态                                                                                                                                                                                                                                       | boolean                                                                                                | -         |          | -        |
| renderPreview     | 预览态模式下渲染的内容<br/><br/>**签名**:<br/>**参数**:<br/>_value_: 文件                                                                                                                                                                          | (value: ObjectFile \| ObjectFile[], props: UploadProps) => void                                        | -         |          | -        |
| fileKeyName       | 文件对象的 key name                                                                                                                                                                                                                                | string                                                                                                 | -         |          | 1.21     |
| fileNameRender    | 自定义文件名渲染<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 文件<br/>**返回值**:<br/>- react node                                                                                                                                                | (file: object) => ReactNode                                                                            | -         |          | -        |
| actionRender      | 自定义操作区域渲染<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 文件<br/>**返回值**:<br/>- react node                                                                                                                                              | (file: ObjectFile) => ReactNode                                                                        | -         |          | -        |
| previewOnFileName | 点击文件名时触发 onPreview                                                                                                                                                                                                                         | boolean                                                                                                | -         |          | 1.24     |
| itemRender        | 自定义成功和失败的列表渲染方式，仅在 listType 是 card/image 时生效                                                                                                                                                                                 | (file: UploadFile, action?: { remove?: () => void }) => ReactNode                                      | -         |          | -        |
| reUpload          | 选择新文件上传并替换                                                                                                                                                                                                                               | boolean                                                                                                | -         |          | -        |

### Upload.Card

继承 Upload 的 API，除非特别说明

| 参数         | 说明                                                                                                                                                             | 类型                                                              | 默认值    | 是否必填 | 支持版本 |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- | --------- | -------- | -------- |
| onPreview    | 点击图片回调                                                                                                                                                     | (file: ObjectFile, e?: MouseEvent\<HTMLElement>) => void          | func.noop |          | -        |
| onChange     | 改变时候的回调                                                                                                                                                   | (value: UploadFile[], file: UploadFile) => void                   | func.noop |          | -        |
| onRemove     | 点击移除的回调                                                                                                                                                   | (file: object) => void                                            | -         |          | -        |
| onCancel     | 取消上传的回调                                                                                                                                                   | () => void                                                        | -         |          | -        |
| itemRender   | 自定义成功和失败的列表渲染方式，仅在 listType 是 card/image 时生效<br/><br/>**签名**:<br/>**参数**:<br/>_file_: 文件对象<br/>_action_: 包含属性 remove: 删除回调 | (file: ObjectFile, action?: { remove?: () => void }) => ReactNode | -         |          | 1.21     |
| reUpload     | 选择新文件上传并替换                                                                                                                                             | boolean                                                           | -         |          | 1.24     |
| showDownload | 展示下载按钮                                                                                                                                                     | boolean                                                           | true      |          | 1.24     |
| onProgress   | 上传中                                                                                                                                                           | (file: UploadFile[], e: UploadFile) => void                       | func.noop |          | -        |

### Upload.Dragger

IE10+ 支持。继承 Upload 的 API，除非特别说明

### Upload.Selecter

[底层能力] 可自定义样式的文件选择器

| 参数            | 说明                                                                                                                                                             | 类型                                      | 默认值    | 是否必填 |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- | --------- | -------- |
| disabled        | 是否禁用上传功能                                                                                                                                                 | boolean                                   | -         |          |
| multiple        | 是否支持多选文件，`ie10+` 支持。开启后按住 ctrl 可选择多个文件                                                                                                   | boolean                                   | false     |          |
| webkitdirectory | 是否支持上传文件夹，仅在 chorme 下生效                                                                                                                           | boolean                                   | -         |          |
| capture         | 调用系统设备媒体                                                                                                                                                 | string                                    | -         |          |
| dragable        | 是否支持拖拽上传，`ie10+` 支持。                                                                                                                                 | boolean                                   | -         |          |
| accept          | 接受上传的文件类型 (image/png, image/jpg, .doc, .ppt) 详见 [input accept attribute](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-accept) | string                                    | -         |          |
| onSelect        | 文件选择回调                                                                                                                                                     | (e: UploadFile[]) => void                 | func.noop |          |
| onDragOver      | 拖拽经过回调                                                                                                                                                     | (e: DragEvent\<HTMLInputElement>) => void | func.noop |          |
| onDragLeave     | 拖拽离开回调                                                                                                                                                     | () => void                                | func.noop |          |
| onDrop          | 拖拽完成回调                                                                                                                                                     | (fiels: File[]) => void                   | func.noop |          |

## Method

### Upload.Uploader

> [底层能力] 文件上传核心功能
> let uploader = new Upload.Uploader([options]);

#### options

| 参数            | 说明                                                                                                      | 类型            | 默认值 |
| --------------- | --------------------------------------------------------------------------------------------------------- | --------------- | ------ |
| action          | 上传的地址                                                                                                | String          | -      |
| data            | 上传额外传参                                                                                              | Object/Function | -      |
| headers         | 设置上传的请求头部                                                                                        | Object          | -      |
| withCredentials | 是否允许请求携带 cookie                                                                                   | Boolean         | false  |
| onProgress      | 上传中<br><br>**签名**:<br>Function() => void                                                             | Function        | noop   |
| onSuccess       | 上传成功回调函数，参数为请求下响应信息以及文件<br><br>**签名**:<br>Function() => void                     | Function        | noop   |
| onError         | 可选参数，上传失败回调函数，参数为上传失败的信息、响应信息以及文件<br><br>**签名**:<br>Function() => void | Function        | noop   |

### 自定义Request

某些场景下需要自定义Request,例如对接AWS S3 jd-sdk or aliyun oss sdk,. Upload 支持 传入自定义的 request方法.

```jsx
function customRequest(option) {
    /* coding here */
    return {
        abort() {
            /* coding here */
        },
    };
}

<Upload request={customRequest} />;
```

customRequest被传入一个 object,包含以下属性:

-   onProgress: (event: { percent: number }): void
-   onError: (event: Error, body?: Object): void
-   onSuccess: (body: Object): void
-   data: Object // 额外的数据
-   filename: String // 文件名
-   file: File // 原生File对象
-   withCredentials: Boolean // 是否携带cookie
-   action: String // 请求地址
-   method: String // 请求类型 post/put
-   timeout: Number // 超时
-   headers: Object // 请求头

request需要返回一个包含abort方法的对象,用于中断上传

`abort(file?: File) => void`: abort the uploading file.

具体实现参照 Upload 默认request方法: <https://github.com/alibaba-fusion/next/blob/master/src/upload/runtime/request.jsx>

### ErrorCode

| ErrorCode           | 含义                                                               |
| ------------------- | ------------------------------------------------------------------ |
| EXCEED_LIMIT        | 当设置了limit, 选中的文件 + 已上传的文件 > limit 报错              |
| BEFOREUPLOAD_REJECT | BeforeUpload中返回了 false/Promise.resolve(false)/Promise.reject() |
| RESPONSE_FAIL       | 返回提响应错误                                                     |

所有的值在`Upload.ErrorCode`.

### onChange 返回结构

```jsx
{
  uid: 'uid',       // 文件唯一标识
  name: 'xx.png'    // 文件名
  state: 'done',    // 状态有：selected uploading done error
  response: {"success":true}  // 服务端响应内容
  url: 'https://img.alicdn.com/tps/TB19O79MVXXXXcZXVXXXXXXXXXX-1024-1024.jpg',
  imgURL: 'https://img.alicdn.com/tps/TB19O79MVXXXXcZXVXXXXXXXXXX-1024-1024.jpg', // 头像(可选)
  downloadURL: 'https://img.alicdn.com/tps/TB19O79MVXXXXcZXVXXXXXXXXXX-1024-1024.jpg'   // 下载(可选)
}
```

### 接口 response 返回数据格式要求

```jsx
{
  "success": true,
  "message": "上传成功",                                  // success=false 时候可以展示错误
  "url": "https://img.alicdn.com/tps/TB19O79MVXXXXcZXVXXXXXXXXXX-1024-1024.jpg",           // 返回结果
  "imgURL": "https://img.alicdn.com/tps/TB19O79MVXXXXcZXVXXXXXXXXXX-1024-1024.jpg",        // 图片预览地址 (非必须)
  "downloadURL": "https://img.alicdn.com/tps/TB19O79MVXXXXcZXVXXXXXXXXXX-1024-1024.jpg"    // 文件下载地址 (非必须)
}
```

### 后端数据格式化

通过 `formatter` 将来自后端的不规则数据转换为符合组件要求的数据格式

-   `假设` 服务器的响应数据如下

```jsx
{
  "status": "success",                              // 上传成功返回码
  "img_src": "https://img.alicdn.com/tps/TB19O79MVXXXXcZXVXXXXXXXXXX-1024-1024.jpg",   // 图片链接
}
```

-   转换方法

```jsx
<Upload
    action="http://127.0.0.1:3001/upload"
    formatter={(res, file) => {
        // 函数里面根据当前服务器返回的响应数据
        // 重新拼装符合组件要求的数据格式
        return {
            success: res.status === 'success',
            url: res.img_src,
        };
    }}
/>
```

### Upload 服务端代码样例

Next Upload组件上传文件使用的`multipart/form-data`方式上传文件,具体实现是在支持`FormData`对象的浏览器中使用xhr对象发送formdata。在不支持`FormData`对象的浏览器如IE9, 使用iframe原生表单实现。

各个语言的服务端框架,必然是可以处理`multipart/form-data`类型的请求,并解析出文件。一下给出两种语言的样例代码

-   [Java Springboot 样例](https://github.com/alibaba-fusion/next-upload-java-server)
-   [Node Eggjs 样例](https://github.com/alibaba-fusion/next-upload-node-server)

## 无障碍键盘操作指南

| 按键  | 说明                                                             |
| :---- | :--------------------------------------------------------------- |
| Enter | 1.当组件获取焦点时，按下`Enter`就可以选择文件上传 2.删除上传图片 |


---


## virtual-list

# zh-CN order=0

# 简单用法

使用 VirtualList 最简单的例子。

# en-US order=0

# Basic

A simple case.


---


## virtual-list

# zh-CN order=1

# 设置初始位置

使用 jumpIndex 设置初始位置

# en-US order=1

# Basic

Use jumpIndex to set first item.


---


## virtual-list

# zh-CN order=2

# 不等高的item

使用 jumpIndex 设置初始位置, 并设置 itemSizeGetter

# en-US order=2

# Basic

Use jumpIndex and itemSizeGetter to set first item in visual area.


---


## virtual-list

# VirtualList

-   category: Components
-   family: Util
-   chinese: 虚拟滚动列表

---

虚拟滚动列表。

## 何时使用

主要用于解决大数据情况下的渲染速度问题。组件的设计思想可以看这篇文章 <a href="https://zhuanlan.zhihu.com/p/55329238" target="_blank">https&#x3A;//zhuanlan.zhihu.com/p/55329238</a>。

## API

### VirtualList

| 参数           | 说明                                                                                           | 类型                                                                                                                                           | 默认值                                       | 是否必填 |
| -------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- | -------- |
| children       | 渲染的子节点                                                                                   | React.ReactElement \| Array\<React.ReactElement \| undefined \| null>                                                                          | -                                            |          |
| minSize        | 最小加载数量                                                                                   | number                                                                                                                                         | 1                                            |          |
| pageSize       | 一屏数量                                                                                       | number                                                                                                                                         | 10                                           |          |
| itemsRenderer  | 父渲染函数                                                                                     | (<br/> items: React.ReactNodeArray,<br/> ref: (instance: React.ReactInstance \| null) => React.ReactInstance \| null<br/> ) => React.ReactNode | `(items, ref) => <ul ref={ref}>{items}</ul>` |          |
| threshold      | 缓冲区高度                                                                                     | number                                                                                                                                         | 100                                          |          |
| itemSizeGetter | 获取 item 高度的函数                                                                           | (index?: number) => void                                                                                                                       | -                                            |          |
| jumpIndex      | 设置跳转位置，需要设置 itemSizeGetter 才能生效，不设置认为元素等高并取第一个元素高度作为默认高 | number                                                                                                                                         | 0                                            |          |


---

