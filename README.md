# LLM for Gravitational Wave Classification

This project explores the use of large language models (LLMs) for classifying gravitational wave signals. The data is sourced from Kaggle's gravitational wave detection competition. Dataset link: [Kaggle G2Net Competition](https://www.kaggle.com/competitions/g2net-gravitational-wave-detection/data). To our knowledge, this is the first attempt to apply LLMs to this task.

---

## Project Structure

### 📁 Data

- **Simulated data** comes from the [Kaggle G2Net competition dataset](https://www.kaggle.com/competitions/g2net-gravitational-wave-detection/data). Alternatively, the `GW/` directory also contains prepared data.
- **Real-world data** is extracted using the PyCBC Python library. See the `train.py` file, specifically the KMeans-based real data processing section.

### ⚙️ Data Processing

The notebook `train.ipynb` handles data preprocessing and generation. It covers the full pipeline from raw strain signals to the creation of JSONL input format for LLM training.

### ⬇️ Model Download

Pre-trained models can be downloaded via [ModelScope](https://www.modelscope.cn/home), especially for users based in China.

### 🧠 Training & Evaluation

Training, merging, and evaluation are configured via the following files:

- `llama3_lora_sft.yaml`: Training configuration
- `llama3_merge_config.yaml`: Model merging (LoRA + base model)
- `llama3_lora_test.yaml`: Evaluation/testing

Before running, make sure to `cd` into the `LLaMA-Factory` directory.

---

## 🔧 LLaMA-Factory Modifications

We use a customized version of the [LLaMA-Factory](https://zhuanlan.zhihu.com/p/695287607?utm_source=wechat_session&utm_medium=social&s_r=0). Several directories have been added or modified:

- `data/`: Stores processed ShareGPT-format training data
- `models/`: Contains downloaded LLM parameters
- `merge_models/`: Stores LoRA-merged model checkpoints
- `saves/`: Stores training logs and outputs

⚠️ Note: The full `LLaMA-Factory` folder exceeds 400 GB, so only the processed datasets (simulated + real) are preserved here. For a visual overview of folder structure, see `llamafactory.png`.

---

## 🧪 Evaluation Metric Update

We modified the default accuracy function in `LLaMA-Factory`. The new `ComputeAccuracy` implementation is located at:

