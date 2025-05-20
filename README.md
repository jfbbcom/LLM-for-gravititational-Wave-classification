# LLM-for-gravititational-Wave-classification
A large model is used to handle the classification task of gravitational wave data. The data is sourced from kaagle's gravitational wave classification competition. Link: https://www.kaggle.com/competitions/g2net-gravitational-wave-detection/data. The large model was used for this task for the first time.

# 工作区域
train.ipynb是生成数据以及处理数据的主要文件，训练、合并模型、测试则分别是由llama3_lora_sft.yaml、llama3_merge_config.yaml、llama3_lora_test.yaml三个文件控制（终端首先要进入LLaMA-Factory文件中）。LLaMa-Factory的具体教程可以参考：https://zhuanlan.zhihu.com/p/695287607?utm_source=wechat_session&utm_medium=social&s_r=0。国内下载各大模型可以去魔塔官网。
