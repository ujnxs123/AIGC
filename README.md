# AIGC
Here is a summary of the AIGC tool and a guide to how to use it
# 介绍
本文致力于收集那些好用的AIGC工具，并附上相关的使用指南方便快速定位与上手使用。

## Stable diffusion

## sovits
 注意声音来源质量要高，不要凑时长。
 音频格式结尾以wav结尾
 音频切片后时长保证在3-15s内
 预处理后的数据集保存在dataset-row里
 训练分支一般来说v1会好点
 识别数据集-> 数据预处理 -> 调节超参数 - > 写入配置文件  -> 开始训练（reference-loss越小综合性能越好） -> tensorboard测评 ->选择满意的模型进行推理 (确保模型和配置文件在对应的文件夹下 【模型：./logs/44k ；配置文件 ：./configs)-> 上传原曲（预处理后：去混响和声）- > 音频转换【有哑高音加滤波器可以有效去除，原曲调太低可以用f0自动预测让调正常】   ，em 总之多试多研究
