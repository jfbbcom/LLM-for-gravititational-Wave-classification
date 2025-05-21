# LLM-for-gravititational-Wave-classification
A large model is used to handle the classification task of gravitational wave data. The data is sourced from kaagle's gravitational wave classification competition. Link: https://www.kaggle.com/competitions/g2net-gravitational-wave-detection/data. The large model was used for this task for the first time.

# 工作区域
## 数据 
模拟数据源为https://www.kaggle.com/competitions/g2net-gravitational-wave-detection/data，也可以直接下载GW文件夹下的数据。真实数据来源于python中PyCBC库，具体提取过程见train.py中真实数据构建kmeans部分。
## 数据处理
train.ipynb是生成数据以及处理数据的主要文件，包含了对数据的预处理，到生成输入jsonl的操作。
## 模型下载
关于模型的下载，国内下载各大模型可以去魔塔官网：https://www.modelscope.cn/home。
## 训练
训练、合并模型、测试则分别是由llama3_lora_sft.yaml、llama3_merge_config.yaml、llama3_lora_test.yaml三个文件控制（终端首先要进入LLaMA-Factory文件中）。
LLaMa-Factory的具体教程可以参考：https://zhuanlan.zhihu.com/p/695287607?utm_source=wechat_session&utm_medium=social&s_r=0。
注意一点，本文使用的准确率函数修改过，不是原LLaMa-Factory使用的ComputeAccuracy函数。该函数具体位置为：/Code/LLaMA-Factory/src/llamafactory/train/sft/metric.py,同时上一级文件/home1/lyx/CODE/LLaMA-Factory/src/llamafactory/train/sft/workflow.py也经过了修改。


