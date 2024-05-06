 # AIGC

Hello! Here is a summary of the AIGC tool and a guide to how to use it

# Introduction

This article aims to collect useful AIGC tools and provide relevant user guides for quick positioning and easy adoption. Contributions from everyone are welcome.


[EN](README_EN.md)|[中文](README_CN.md)

## Table of Contents
1. [AI Painting](#ai-painting)  
2. [AI Voice](#ai-voice)
3. [Large Language Models](#large-language-models)
4. [AI Image Processing](#ai-image-processing)
5. [AI Video](#ai-video)
6. [Auxiliary Tools](#auxiliary-tools)

## AI Painting

### Stable Diffusion
`Stable Diffusion` is a Latent Diffusion Model that can generate detailed images from text descriptions. It can also be used for tasks such as image restoration, image drawing, text-to-image, and image-to-image. SD has richer personalization features compared to Midjourney. After user training, it can generate images closer to the requirements. Combined with some plugins and fine-tuning, it can produce some stunning images. Its biggest advantage is that it is open source and freely usable.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official webui|[git](https://github.com/AUTOMATIC1111/stable-diffusion-webui)|
|(Akiye version) Integration package|[Baidu Netdisk](https://pan.baidu.com/s/11xBdZGdaaUfQpOCAGLyq6w?pwd=5bsf )(Extraction code:5bsf) |

It's actually very simple to deploy and run locally. In fact, there are comprehensive tutorials in the repository. It is recommended to directly use Anaconda when downloading Python for convenient package management. Before deploying the environment, use `conda create -n your_env_name python=x.x` to create a virtual environment, and then use `conda activate your_env_name` to download the required dependencies in it.

Using an integration package is what I recommend more. It saves time and effort, and is a one-stop solution. The environment is completely enclosed and does not affect the risk of local packages.

Of course, it's easy to use, but to use it well and make it draw the effects I want, it requires some research. If you are interested, you can watch the videos of [Newly](https://space.bilibili.com/1814756990). I think they are very well explained and easy to understand.

I recommend a website for downloading various painting models, [Civitai: The Home of Open-Source Generative AI](https://civitai.com/), which requires scientific Internet access.

### Lora Script
`lora script` is a webui developed by Akiye that can visually train lora models on the interface. The interface is very good-looking and easy to use. It comes with official documentation, and the author has thoughtfully added one-click configuration environment scripts for both Windows and Linux. If you have related needs, it is highly recommended.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official webui|[git](https://github.com/Akegarasu/lora-scripts)|
|(Akiye version) Integration package|[Baidu Netdisk](https://pan.baidu.com/s/1np8plThzVIIPPXvJ30SXPw?pwd=px90)(Extraction code: px90) |

### Midjorney

### **Shape-e**
`shap-e` is a new model open-sourced by OpenAI, used to generate 3D objects conditioned on text or images. Its usage is also very simple, just install a package: `pip install -e `

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/openai/shap-e)|

## AI Voice

-   _**Text-to-Speech (TTS)**_: High-performance, supports mainstream models and architectures, and can generate natural sounds.
-    _**Singing Voice Conversion (SVC)**_: Can convert one person's singing voice to another person's. Built-in trained voices include Jacky Cheung, Eason Chan, Faye Wong, etc.
-   _**Text-to-Audio (TTA)**_: Can generate realistic sound effects, speech, and music through text prompts.

In the audio field, there are many AIGC tools selflessly open-sourced by great gods, such as the sovits model famous for cyborg singing, and the bert-voits model with the best effect in the field of text-to-speech with emotion. However, these two models have high requirements for the training set. The clean voice duration must be at least half an hour to have a better effect, which requires some effort to fine-tune. The character voices we want to train mostly have relatively short audio durations. We can make a compromise and give up some accuracy. gpt-sovits is a relatively new tool that can achieve a very good effect with a relatively small dataset.

### OpenVoice

### SO-VITS-SVC

Note that the sound source quality should be high, and don't just make up the duration.

Audio format should end with wav.

Ensure the duration of audio slices is between 3-15s.

Save the preprocessed dataset in dataset-row.

The v1 branch is generally better for training.

Recognize dataset -> Data preprocessing -> Adjust hyperparameters -> Write configuration file -> Start training (the smaller the reference-loss, the better the overall performance) -> tensorboard evaluation -> Select a satisfactory model for inference (ensure the model and configuration file are in the corresponding folders [Model: ./logs/44k; Configuration file: ./configs) -> Upload the original song (preprocessed: remove reverberation and vocals) -> Audio conversion [Adding a filter can effectively remove harsh highs; if the original pitch is too low, f0 automatic prediction can be used to make the pitch normal], em Anyway, try more and study more

### BERT

### GPT-SoVits (TTS)
·`Low dataset requirements`, this is the biggest advantage of this project. With a dataset of one or two minutes, after labeling, the total training time does not exceed three minutes, and a very good effect can be obtained.
Specific operations can follow this [tutorial](https://zhuanlan.zhihu.com/p/679368007), which is very detailed.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/RVC-Boss/GPT-SoVITS)|
|Integration package|[Baidu Netdisk](https://pan.baidu.com/s/1COzOmtYQv6oM6fOl6r8OQw?pwd=ok84)(Extraction code: ok84) |

## AI Image Processing

### DDColor
`DDColor` is an _**image colorization model**_ based on deep learning technology researched by _**Alibaba DAMO Academy**_. It can automatically color black-and-white or grayscale images to make the images more vivid and realistic.
This model adopts advanced neural network architecture and training techniques, and can recognize objects and scenes in images and add realistic colors to them.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/piddnad/DDColor)|

`It should be noted that with the help of plugins, stable difuusion can also achieve re-coloring of images, but in fact it will also partially redraw the picture at the same time, and the effect is average.`

## Large Language Models
### **Autogen**
`Autogen` is a multi-agent framework developed by the Microsoft team. It can easily customize a series of work tasks, and its core is the large language model.
-   Define an `Assistant Agent`, whose task is to solve problems
-    Define a `UserProxy Agent`, whose task is to ask questions on behalf of people and execute programs locally

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/microsoft/autogen)|

### **Lobe Chat**
`Lobe Chat` is an out-of-the-box one-click deployment private GPT/LLM chatbot.
This is an open-source, free, high-performance chatbot framework that supports speech synthesis, multimodal, and an extensible plugin system. It can be networked, draw pictures, crawl, etc. The interface is very beautiful and also supports one-click deployment.

The reason for recommending it is still multimodal, built-in crawler, and beautiful interface.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/lobehub/lobe-chat)|

## AI Video

###  **Video-Retalking**
`Video-ReTalking` is an innovative technology that uses AI to synchronize the lip movements of video characters with the input voice. Simply put, by inputting any video and an audio file, in the generated new video, the _**character's lip movements will be synchronized with the audio.**_

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/OpenTalker/video-retalking)|

## Auxiliary Tools
### Slidev
`Slidev` is a presentation tool specifically designed for developers. With Slidev, we can make cool PPTs by simply using the familiar Markdown, while having the ability to support HTML and Vue components, and can present pixel-perfect layouts.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/slidevjs/slidev)|

### **Pake**
`Pake` can package web pages into desktop applications. It is very suitable for people who want to package WEB applications. After all, Web applications can only be used based on browsers, while Pake can package them as standalone applications. Compared with traditional `Electron` packaging, the application packaged by Pake is about 20 times smaller in size, and the performance and experience are also better than JS frameworks.
Pake not only can simply package web pages, but also implements features such as shortcut key passthrough, immersive window, drag and drop, style rewriting, ad removal, etc., which can deeply customize the style of the product.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/tw93/Pake)|

### **DevToys**
`DevToys` is a collection of tools for developers, including various practical gadgets and auxiliary functions, aiming to improve development efficiency and simplify the development process. The project covers multiple tools and plugins, covering different development fields, including but not limited to text comparison, encoding/decoding, image compression, formatting, converters and generators, etc. Its goal is to provide developers with a platform that integrates various practical tools and plugins to help them work more efficiently.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/veler/DevToys)|

### **movie-web**
`Cyberpunk Movie Watching`
**movie-web** is a movie information website project based on `React` and `Node.js`, aiming to provide users with convenient and fast movie information browsing and search functions.
This project adopts modern front-end and back-end technologies to provide users with a good user experience and stable service.
Nothing special, clean and hygienic, no ads.

Secondly, it can be used as a practical project to learn React and Node.js technologies, and can also be used as a basic framework for movie information websites for secondary development and customization.  

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/movie-web/movie-web)|

### **RustDesk**
`RustDesk` is an open-source remote desktop developed domestically, supporting multiple platforms such as `Windows, macOS, Liunx, IOS, Android, Web`, etc. It is also very simple to use, just download the latest release version for the corresponding platform.

**Project Acquisition**
|Type |  Resource Address|
|-|-|
|Official|[git](https://github.com/rustdesk/rustdesk/releases/)|