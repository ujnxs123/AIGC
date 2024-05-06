# AIGC

Hello！Here is a summary of the AIGC tool and a guide to how to use it

# 介绍

本文致力于收集那些好用的AIGC工具，并附上相关的使用指南方便快速定位与上手使用。也欢迎大家一起补充。

[EN](README_EN.md)|[中文](README.md)

## 目录
1. [ai绘画](#ai绘画)  
2. [ai语音](#ai语音)
3. [大语言模型](#大语言模型)
4. [ai图像处理](#ai图像处理)
5. [ai视频](#ai视频)
6. [辅助小工具](#辅助小工具)



  

## ai绘画

### stable diffusion
`Stable Diffusion`是一种潜在扩散模型（Latent Diffusion Model），能够从文本描述中生成详细的图像。它还可以用于图像修复、图像绘制、文本到图像和图像到图像等任务。SD拥有比Midjourney更加丰富的个性化功能，在经过使用者调教后可以生成更贴近需求的图片，配合一些插件以及微调，能得到一些非常惊艳的图片。其最大的优势就是开源与使用自由。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方webui|[git](https://github.com/AUTOMATIC1111/stable-diffusion-webui)|
|(秋叶版)整合包|[百度网盘](https://pan.baidu.com/s/11xBdZGdaaUfQpOCAGLyq6w?pwd=5bsf )(提取码:5bsf) |

 
想部署在本地运行实际上是很简单的，实际上在仓库里已经有了全面的教程，。建议下载python时直接使用anaconda，方便进行包管理。部署环境前先使用`conda create -n your_env_name python=x.x`创建虚拟环境，再使用`conda activate your_env_name`　在里面下载所需的依赖环境

使用整合包是本人比较推荐的，省时省力，一步到位，谁也别说谁，环境全封闭，也没有影响本地包的风险。

当然，想用上市很简单的，但是想用好，想让其画出我想得到的效果，就需要研究一下。有兴趣的可以看这位 [Newly同学](https://space.bilibili.com/1814756990)的视频。个人认为讲的很好，通俗易懂。

推荐一个下载各种绘画模型的网站，[Civitai: The Home of Open-Source Generative AI](https://civitai.com/)，需要科学上网。

  
### Lora Script
`lora script` 是由秋ye大佬开发出的一个可以在界面上可视化训练lora模型的webui，页面很好看也很好用。自带官方文档，大佬非常贴心的加上了在windows与linux都能一键配置环境的脚本，如果由相关需求，非常推荐。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方webui|[git](https://github.com/Akegarasu/lora-scripts)|
|(秋叶版)整合包|[百度网盘](https://pan.baidu.com/s/1np8plThzVIIPPXvJ30SXPw?pwd=px90)(提取码: px90) |
|



### midjorney

### **shape-e**
`shap-e` 是OpenAI开源的一款新模型，用来生成以文本或图像为条件的 3D 对象。它的使用也非常简单，安装一个包即可： `pip install -e `

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/openai/shap-e)|


  
  

## ai语音

-   _**文本转语音（TTS）**_：高性能，支持主流模型及架构，可生成自然的声音。
-    _**歌声转换（SVC）**_：可将某人歌声转换成其他人歌声，内置张学友、陈奕迅、王菲等已训练好的声音。
-   _**文本转音频（TTA）**_：可通过文本提示，生成逼真的声效、语音以及音乐。

音频领域有许多大神无私开源出来的AIGC工具，像以赛博翻唱闻名的sovits模型，在赋予感情的文本转语音领域效果最好的模型bert-voits，但是这两个模型对训练集要求很高，干声时长至少要半个小时才会有比较好的效果，需要花点精力微调。咱们想要训练的角色语音大多语音时长比较短，可以退而求其次的舍弃掉一定的精度去。gpt-sovits是比较新的工具，比较少的数据集就可以得到一个相当不错的效果。

### openvoice

### so-vits-vs

注意声音来源质量要高，不要凑时长。

音频格式结尾以wav结尾

音频切片后时长保证在3-15s内

预处理后的数据集保存在dataset-row里

训练分支一般来说v1会好点

识别数据集-> 数据预处理 -> 调节超参数 - > 写入配置文件 -> 开始训练（reference-loss越小综合性能越好） -> tensorboard测评 ->选择满意的模型进行推理 (确保模型和配置文件在对应的文件夹下 【模型：./logs/44k ；配置文件 ：./configs)-> 上传原曲（预处理后：去混响和声）- > 音频转换【有哑高音加滤波器可以有效去除，原曲调太低可以用f0自动预测让调正常】 ，em 总之多试多研究

### bert

  

### gpt-sovits（TTS）
·`数据集要求不高`，这是该项目最大的有点，一段一两分钟的数据集，打上标之后，前后训练时间不超过三分钟，就可以得到非常不错的效果。
具体操作可以跟着这个[教程](https://zhuanlan.zhihu.com/p/679368007),非常详细。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/RVC-Boss/GPT-SoVITS)|
|整合包|[百度网盘](https://pan.baidu.com/s/1COzOmtYQv6oM6fOl6r8OQw?pwd=ok84) (提取码: ok84)|


## ai图像处理

### DDColor
`DDColor` 是一个由 _**阿里达摩院**_ 研究的基于深度学习技术的 _**图像上色模型**_，它能够自动将黑白或灰度图像着色，使图像更加生动逼真。
该模型采用了先进的神经网络架构和训练技术，能够识别图像中的物体和场景，并为其添加逼真的颜色

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/piddnad/DDColor)|

`需要注意的是，借助插件，stable difuusion也能实现对图片的再上色，但事实上同时也会对画面进行部分重绘，效果差强人意。`

## 大语言模型
### **autogen**
`Autogen` 是微软团队研发的一个多代理框架，利用它可以轻松定制一系列工作任务，其核心正是大语言模型。
-   定义一个 `Assistant Agent`，它的任务是解决问题
-    定义一个 `UserProxy Agent`，它的任务是替代人询问问题，同时在本地执行程序

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/microsoft/autogen)|


### **Lobe Chat**
`Lobe Chat` 是一款开箱即用一键部署私人 GPT/LLM 的聊天机器人。
这是一个开源免费的高性能聊天机器人框架，支持语音合成、多模态和可扩展的插件系统，可以联网、画图、爬虫等。这个界面非常漂亮，同时也支持一键部署。

推荐使用的原因还是多模态，自带爬虫，界面漂亮。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/lobehub/lobe-chat)|

## ai视频

###  **Video-Tetalking**
`Video-ReTalking` 是一个利用AI实现视频人物嘴型与输入的声音同步的创新技术。简单来说，就是输入任意一个视频和一个音频文件，在生成的新视频中，_**人物的嘴型会与音频同步。**_

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/OpenTalker/video-retalking)|


## 辅助小工具
### slidev
`Slidev` 是一款专门为开发者打造的演示文稿工具。通过Slidev，我们只要使用熟悉的Markdown就可以做出炫酷的PPT来，同时拥有支持HTML和Vue组件的能力，并且能够呈现像素级完美的布局。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/slidevjs/slidev)|

### **Pake**
`Pake` 可以将网页打包成桌面应用。很适合想打包WEB应用的人群进行使用。毕竟Web应用只能基于浏览器进行使用，而Pake可以将其打包作为独立应用进行使用。相比传统的 `Electron` 打包，Pake 打包出来的应用体积小20倍左右，并且性能和体验也优于JS框架。
Pake 不仅可以简单地打包网页，还实现了快捷键透传、沉浸式窗口、拖拽、样式改写、去广告等功能，可以深度定制产品的风格。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/tw93/Pake)|

### **DevToys**
`DevToys` 是一个用于开发者的工具集合，包括各种实用的小工具和辅助功能，旨在提高开发效率和简化开发过程。该项目涵盖了多个工具和插件，涵盖了不同的开发领域，包括但不限于文本对比、编解码、图像压缩、格式化、转换器及生成器等。它的目标是为开发者提供一个集成了各种实用工具和插件的平台，帮助他们更高效地进行开发工作。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/veler/DevToys)|

### **movie-web**
`赛博看电影`
**movie-web** 是一个基于 `React` 和 `Node.js` 的电影信息网站项目，旨在为用户提供方便快捷的电影信息浏览和搜索功能。
该项目采用现代化的前端技术和后端技术，为用户提供良好的用户体验和稳定的服务。
没啥特别的意思，干净又卫生，无广告。

其次是可以学习一下React和Node.js技术的实践项目，也可以作为电影信息网站的基础框架，进行二次开发和定制化。  

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/movie-web/movie-web)|

### **RustDesk**
`RustDesk`是一款国产开发开源的远程桌面，支持 `Windows、macOS、Liunx、IOS、Android、Web` 等多个平台。使用也很简单，直接下载对应平台的最新发布版即可。

**项目获取**
|类型 |  资源地址|
|-|-|
|官方|[git](https://github.com/rustdesk/rustdesk/releases/)|
