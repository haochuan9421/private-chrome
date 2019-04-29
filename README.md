# 无痕 Google Chrome

谷歌浏览器目前设置项里 **无法设置启动时默认打开无痕模式**，不过可以通过 Mac 电脑自带的 **脚本编辑器** 来创建一个应用，以无痕模式唤起 Chrome。方法也很简单，下面是详细步骤:

### Step1 - 通过 **脚本编辑器** 创建一个脚本

<img src="https://user-images.githubusercontent.com/5093611/56876624-54ef4780-6a7b-11e9-919a-b863ab0bcd0f.png" width="300"/>

<img src="https://user-images.githubusercontent.com/5093611/56876660-95e75c00-6a7b-11e9-8e51-69899c48c844.png" width="500" />

### Step2 - 复制下面这段代码👇到编辑器

```bash
if application "Google Chrome" is running then
	tell application "Google Chrome"
		make new window with properties {mode:"incognito"}
	end tell
else
	do shell script "open -a 'Google Chrome' --args --incognito "
end if
```

### Step3 - 保存为 **应用程序**

<img src="https://user-images.githubusercontent.com/5093611/56876710-e363c900-6a7b-11e9-9e26-ab668aadef9a.png" width="500" />

至此点击这个程序就可以实现直接启动 Chrome 无痕模式的效果了，但是它的 LOGO 会是默认的，并不怎么好看。

<img src="https://user-images.githubusercontent.com/5093611/56876790-5cfbb700-6a7c-11e9-8493-985382ad1fed.png" />

### Step4 - 自定义 LOGO

这个 [仓库](https://github.com/alrra/browser-logos) 提供了很多浏览器的 LOGO，你可以从中挑选自己喜欢的一个，比如我就挑选了 [IE9](https://github.com/alrra/browser-logos/tree/master/src/archive/internet-explorer_9-11) 的 👻，把下面这几种尺寸的下载下来到 `somename.iconset` 文件夹就可以了。

<img src="https://user-images.githubusercontent.com/5093611/56876881-0773da00-6a7d-11e9-9be3-e64a815e4107.png" />

打开 **终端**，执行下面这行命令，就会生成一个 `icns` 图标文件

```bash
iconutil --convert icns ./ie.iconset/
```

<img src="https://user-images.githubusercontent.com/5093611/56876964-718c7f00-6a7d-11e9-9123-388331c48046.png" width="500">

然后点击刚才创建的应用程序，`CMD + i` 查看详情，把生成的图标文件拖动到详情上面的图标上进行覆盖就可以了，🎉🎉🎉👏👏👏，大功告成，你可把应用放到 **应用程序** 目录并添加到 `Dock` 栏，这样以后通过这个自己的小应用，你都可以很方便的直接打开 `Chrome 浏览器` 的无痕模式了！

<img src="https://user-images.githubusercontent.com/5093611/56877114-566e3f00-6a7e-11e9-8676-0c3b53b23797.png" width="500">

