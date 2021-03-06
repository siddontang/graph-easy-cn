# 输出

阅读本章之前，请先阅读[概论](overview/README.md)

本章说明了Graph::Easy支持的输出格式以及各种格式的限制，优点以及缺点。

## 格式

Graph::Easy可以产生如下几种输出格式：

- ASCII：使用ASCII art绘制图形
- Box Art: 使用Unicode的"box drawing" 字符创建文本图形
- HTML: 使用HTML+CSS代码来渲染图形
- SVG: 产生可伸缩矢量图形输出

另外，可以用以下几种描述语言来描述图形：

- txt: Graph::Easy自定义的文本描述语言，用Graph::Easy的解析起解析
- graphviz : 使用graphviz语言，可以通过某些外部程序比如`dot` 生成PNG, SVG等输出
- GraphML : [GraphML语言](http://graphml.graphdrawing.org/)
- yED : [yED语言](http://www.yworks.com/de/products_yed_about.html)

## ASCII

ASCII格式的输出只能有两种颜色，一个是前景色，一个是背景色。

```
  #============================================#
  H                                            v
+---------+     ........     +---------+     +--------+     +--------+
| Bautzen | --> : Bonn : --> | Koblenz | --> | Berlin | --> | Kassel |
+---------+     :......:     +---------+     +--------+     +--------+
  ^               |            ^               ^
  :               +------------+---------------+
  :                            |
  :             +------+       |
  ............. | Ulm  | ------+
                +------+
```

这种格式有如下限制：

- 不论真实的边的箭头如何，这种格式的箭头永远是打开的
- 节点的形状不支持多边形或者圆角
- 以下几种边`bold`, `broad`和`wide`都用`#`渲染，因此看起来是一样的.

## Box Art

这种方式和`ASCII`原理差不多，但是使用它Unicode的`box art`字符；这种方式边角之间的空隙更小，因此看起来效果好很多。`Box Art`和`ASCII`的限制差不多，但是有以下不同：

- 边角看起来更好
- 支持圆角
- 支持不同的箭头风格
- 边的几种风格`bold`, `broad`和`wide`可以正常使用

```

                                My sample graph

                                             Test
                                             label
            ┌···············································┐
            :                                               v
          ┌─────────────┐  label   ▛▀▀▀▀▀▀▜               ┌───────┐
          │     One     │ ───────> ▌ Two  ▐ ▬▬▬▬▬▬▬▬▬▬▬▬> │ Four  │ ···   None
          └─────────────┘          ▙▄▄▄▄▄▄▟               └───────┘
            ║                                Test label
            ║                        ┌╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴╴┐
            v                        ╵                      v
          ┌−−−−−−−−−−−−−┐          ████████               ┏━━━━━━━┓     ┌───────┐
  ┌·······╎    Three    ╎ <══════> █ Five █ ────────────> ┃ Seven ┃ ─── │ Eight │
  :       └−−−−−−−−−−−−−┘          ████████               ┗━━━━━━━┛     └───────┘
  :         ^                        │                                    ^
  :         │                        │                                    │
  : Test    │ Test label             └────────────────────────────────────┘
  : label   v
  :       ┌─────────────┐
  :       │    Sixty    │
  :       │    Six      │
  :       │    and      │
  └······>│    six      │
          └─────────────┘
```

## HTML

HTML效果看起来如下：

<img src="http://7xp3xc.com1.z0.glb.clouddn.com/201512/1452943758040.png" width="263"/>

## SVG/GraphML/yED
略
